## devops-netology

# Файлы, которые будут пропущены благодаря terraform/.gitignore

- Все файлы внутри скрытой директории .terraform, которая находится на любой глубине вложения диретории terraform
- Файлы с расширенеим tfstate
- Файлы, содержащие в имени .tfstate.
- Файл crash.log
- Все файлы с расширением tfvars
- Файлы override.tf override.tf.json terraform.rc .terraformrc
- Файлы, который оканчиваются на _override.tf _override.tf.json
