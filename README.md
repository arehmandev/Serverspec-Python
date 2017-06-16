# Serverspec-Python
Python script for executing serverspec tests locally - useful as an ansible task

Just clone this, put your tests in the Tests directory and run python serverspec.py

Example use in a task:

```
- name: Copy over serverspec tests to remote location
  copy:
  src: "{{ role_path }}/Serverspec-Python
  dest: /etc/serverspec_tests
  owner: root
  group: root
  mode: "u=rw,g=r,o=r"

- name: Execute serverspec tests
  script: /etc/serverspec_tests/serverspec.py
```

Future goal:

Turn this into an ansible module for serverspec tests in this format:

```
- name: Run serverspec tests after role completes
  serverspec:
    file: “tests/mytest.rb”
```
