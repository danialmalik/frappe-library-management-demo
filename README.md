## Library Management

Library Management System

## Setup

**IMPORTANT**: Since we are going to use `postgres` databse, please make sure to use this database
while setting up bench and other related operations.

1. Install and setup frappe-bench by following this guide: https://frappeframework.com/docs/v13/user/en/tutorial/install-and-setup-bench
2. Clone this frappe app using the following command inside the bench directory:

```sh
bench get-app git@github.com:danialmalik/frappe-library-management-demo.git
```

There should be a directory `library_management` inside `apps/` directory.

3. Now we need to setup a site to use this app. Add a new site with this command:

```sh
bench new-site library.test --db-type "postgres"
```

Enter root credentials for your postgres db. This command will setup a new site `library.test` for this app.

When asked, setup an administrator password. Remember this password as this password will be used to
access the site for the first time.

4. Now we need to link our app to this site by running this command:

```sh
bench --site library.test install-app library_management
```

5. The last step is to update the `hosts` file to point this site to localhost.

Use this command to open the file:

```sh
sudo vim /etc/hosts
```

and add this line at the end of file:

```sh
127.0.0.1      library.test
```

and save.

6. Now we are finally ready to start the app. Run this command to start the bench:

```sh
bench start
```

7. You can access your site at `http://library.test:8000` now. Use `Administrator` as username and the admin password you set at step 3 to login.


#### License

MIT
