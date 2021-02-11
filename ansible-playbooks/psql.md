## Postgresql Installation using Ansible playbook:

	### Steps1 :
        Configure Postgres server IP in ansible server host file
        
        ```
        [build-server]
         10.0.0.80
       ```

	### Install latest version of bash and OpenSSl
	
	### Install python using below
  ```
      command: pip3 install psycopg2-binary
	```
	###  Install postgresql and postgresql-contrib,postgresql-server
  
  ```
    - name: Installing postgresql
      yum:
       name: postgresql
       update_cache: true
       state: latest
    - name: Installing postgresql-contrib
      yum:
       name: postgresql-contrib
       update_cache: true
       state: latest
    - name: Installing postgresql-server
      yum:
       name: postgresql-server
       update_cache: true
       state: latest
   ```
	###  Check and Ensure if PostgreSQL database is initialized.
		```
    - name: Check if PostgreSQL database is initialized.
      stat:
       path: "{{ postgresql_data_dir }}/PG_VERSION"
      register: pgdata_dir_version

    - name: Ensure PostgreSQL database is initialized.
      command: "{{ postgresql_bin_path }}/initdb -D {{ postgresql_data_dir }}"
      when: not pgdata_dir_version.stat.exists
      become: true
      become_user: "{{ postgresql_user }}"
      vars:
       ansible_ssh_pipelining: true
   ```
	   
	  ### Starting postgresql by shell
    ```
      shell: systemctl start postgresql
    ```
	  
	  ### Create Postgres DB and USer using the modules postgresql_db,postgresql_user
	  ```
	  - name: Ensure database is created
      postgresql_db:
       name: sonar
       encoding: UTF-8
       lc_collate: en_US.UTF-8
       lc_ctype: en_US.UTF-8
       template: template0
       state: present
    - name: Ensure user has access to the database
      postgresql_user:
       db: sonar
       name: sonar
       password: "{{ sonarpassword }}"
       priv: ALL
       state: present
	  ```
	  ### Provide the password in Ansible Valut file and import the valut file in ansible playbook using vars_files module
	```
    vars_files:
        - vault-pass.yml
  ```
