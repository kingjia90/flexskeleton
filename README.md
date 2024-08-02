# Pimcore Symfony Flex Skeleton

1. Clone this repository
2. Run `composer install`
3. It would ask about adding new config and docker, reply `y` to both
![image](https://github.com/user-attachments/assets/b27af085-5839-40e2-8c3c-db30cde0b28b)


4. Docker: Fix `compose.yaml` user and user group id
5. Start the needed services with `docker compose up -d`
6. Install pimcore and initialize the DB `docker compose exec php vendor/bin/pimcore-install`

## Test public repository

`composer require pimcore/web-to-print-bundle` and it would ask to run the recipe, press `y` and would copy the controller, template, var/config and add the entry in `bundles.php`

## Test private repositories

`composer require pimcore/portal-engine` and it would ask to run the recipe, press `y` and would copy the controller, template and config 
> [!WARNING]  
> There should be a `symfony.lock` in the portal engine to avoid being prompted to install the recipes that are not necessary.



## Notes
- It would be possible to avoid docker compose yaml changes by pressing `n` but the `.docker` folder is copied regardless, it would be nice to be able to avoid it, in case somebody don't need docker.
- The `.env` file seems necessary to be able to append the env variables from the recipes, when the `.env` file is not present, it would skip
