# app-greenshot
Greenshot is a light-weight screenshot software tool for Windows.

Howto
----------------
This role is designed for a controlled environment (e.g. RDS / VDI) with an own (internal)webserver for hosting packages.  

1. Add variable {{ def_ans_repo }} to your group_vars or change it in your playbook or role.
2. Zip all files in 1 file.
3. Upload the file to the web/download server.
4. Edit defaults/main.yml to your needs.
5. Add the role to your playbook.

Example Playbook
----------------

This is an basic example, how to use the role:

    - hosts: windows_computers

      vars:

      roles:
        - app-greenshot



This is an example how to use the role with custom variable(s):

    - hosts: windows_computers
      become: true

      vars:
        # -- custom settings - app-greenshot --
        pkg_arguments: 'IACCEPTMSOLEDBSQLLICENSETERMS=YES ADDLOCAL=ALL'

      roles:
        - app-greenshot

Source(s)
----------------
* https://getgreenshot.org/