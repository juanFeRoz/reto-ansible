# reto-ansible

## verificar conexion con nodos
´ansible all -i inventario.ini -m ping´

## ejecutar el playbook
´ansible-playbook -i inventario.ini configurar_servidores.yml´

## verificar idempotencia
Despues de la primera ejecucion del playbook hay que correr ´ansible-playbook -i inventario.ini configurar_servidores.yml´ de nuevo y verificar que el reporte final debería mostrar ´changed=0´ o muy pocos cambios

## crear vault para contraseñas y secretos
´ansible-vault create vars/secret.yml´ se abrira un editor de texto y hay que poner los secretos en el siguente formato:
´ssh_user_password: "UnaContraseñaMuySegura_1234"´

### usar ansible con el vault
´ansible-playbook -i inventario.ini mi_playbook.yml --ask-vault-pass´
