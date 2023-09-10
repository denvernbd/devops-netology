# devops-netology

Добавлю нулевую строку! для проверки второго занятия.

Добавлю сюда эту строчку.

Добавлю сюда вторую строку.
 
Пожалуй и третью.

в будущем благодаря добавленному .gitignore будут проигнорированы:

```bash
# Local .terraform directories
**/.terraform/*
```
- каталог ".terraform" находящийся в любых каталогах

```bash
# .tfstate files
*.tfstate
*.tfstate.*
```
- файлы заканчивающиеся на ".tfstate" и содержащие в названии "любойСимвол.tfstate.любойСимвол"

```bash
# Crash log files
crash.log
crash.*.log
```
- файлы "crash.log" и все файлы содержащие в названии "crash.любоеСимвол.log"

```bash
# Exclude all .tfvars files, which are likely to contain sensitive data, such as
# password, private keys, and other secrets. These should not be part of version 
# control as they are data points which are potentially sensitive and subject 
# to change depending on the environment.
*.tfvars
*.tfvars.json
```
- файлы с расширением ".tfvars" и все файлы оканчивающиеся на ".tfvars.json"

```bash
# Ignore override files as they are usually used to override resources locally and so
# are not checked in
override.tf
override.tf.json
*_override.tf
*_override.tf.json
```
- конкретные файлы override.tf и override.tf.json и файлы подпадающие под маску *_override.tf *_override.tf.json


```bash
# Include override files you do wish to add to version control using negated pattern
# !example_override.tf
```
- тут мы указываем что необходимо добавить файл "example_override.tf"

```bash
# Include tfplan files to ignore the plan output of command: terraform plan -out=tfplan
# example: *tfplan*
```
- все файлы содеражщие в названии "*tfplan*"

```bash
# Ignore CLI configuration files
.terraformrc
terraform.rc
```
- конкретные файлы .terraformrc и terraform.rc
