---
layout: post
title: Testing Architecture with Python
date: 2025-03-05 10:39
category: development
author: Ilia Kaziamov
tags: [python, testing, architecture]
---

How to test architecture? After all, in Python you can do a lot, since many restrictions exist at the word level, not at the code level. In real projects, descriptions of approaches may be in Confluence, which is very far from the code. This is often forgotten, skipped or ignored when tasks are burning.

For example, if desired, in a project you can send a request to the database from a view, serializer, or any other place in the code. Essentially, no one will do anything. In a review, this can be missed, laying a time bomb in the codebase that will lead to refactoring for many person-hours in the future.

Trips to the database are an extreme example. However, essentially, this can be any other action happening not where it should. To automate the process and reduce the number of human errors, you can write tests for architecture. For example, when using the DDD approach with onion architecture, you can encapsulate the domain layer and check that only allowed imports are used inside this domain. This applies to any layer and package to avoid imports of packages, modules and frameworks that don't belong here.

A simple example of such a test that can be adapted to your needs:

```python
import importlib
import pkgutil

def list_modules(package_name):
    package = importlib.import_module(package_name)
    modules = []
    for _, module_name, is_pkg in pkgutil.walk_packages(package.__path__, package.__name__ + '.'):
        modules.append(module_name)
        if is_pkg:
            modules.extend(list_modules(module_name))
    return modules

def test_check_isolated_domain_layer():
    accepted_layers = ["domain"]
    root = 'src'
    modules = list_modules(root)
    for module in modules:
        imported_module = module.split('.')[1]
        for layer in accepted_layers:
            assert imported_module == layer, f'Module "{module}" is not in accepted layers: "{accepted_layers}"'
```

Reading code in Telegram isn't very convenient, so here's a [link to this code on GitHub](https://github.com).
