# Error-Uncaught-ArgumentCountError-array_merge-does-not-accept-unknown-named-parameter-.php-84
PHP Fatal error:  Uncaught ArgumentCountError: array_merge() does not accept unknown named parameters in /usr/share/php/Composer/DependencyResolver/DefaultPolicy.php:84

**EORROR OUTPUT**:
```
Stack trace:
#0 [internal function]: array_merge()
#1 /usr/share/php/Composer/DependencyResolver/DefaultPolicy.php(84): call_user_func_array()
#2 /usr/share/php/Composer/DependencyResolver/Solver.php(387): Composer\DependencyResolver\DefaultPolicy->selectPreferredPackages()
#3 /usr/share/php/Composer/DependencyResolver/Solver.php(740): Composer\DependencyResolver\Solver->selectAndInstall()
#4 /usr/share/php/Composer/DependencyResolver/Solver.php(231): Composer\DependencyResolver\Solver->runSat()
#5 /usr/share/php/Composer/Installer.php(489): Composer\DependencyResolver\Solver->solve()
#6 /usr/share/php/Composer/Installer.php(232): Composer\Installer->doInstall()
#7 /usr/share/php/Composer/Command/UpdateCommand.php(163): Composer\Installer->run()
#8 /usr/share/php/Symfony/Component/Console/Command/Command.php(255): Composer\Command\UpdateCommand->execute()
#9 /usr/share/php/Symfony/Component/Console/Application.php(934): Symfony\Component\Console\Command\Command->run()
#10 /usr/share/php/Symfony/Component/Console/Application.php(273): Symfony\Component\Console\Application->doRunCommand()
#11 /usr/share/php/Composer/Console/Application.php(281): Symfony\Component\Console\Application->doRun()
#12 /usr/share/php/Symfony/Component/Console/Application.php(149): Composer\Console\Application->doRun()
#13 /usr/share/php/Composer/Console/Application.php(113): Symfony\Component\Console\Application->run()
#14 /usr/bin/composer(62): Composer\Console\Application->run()
#15 {main}
  thrown in /usr/share/php/Composer/DependencyResolver/DefaultPolicy.php on line 84

Fatal error: Uncaught ArgumentCountError: array_merge() does not accept unknown named parameters in /usr/share/php/Composer/DependencyResolver/DefaultPolicy.php:84
Stack trace:
#0 [internal function]: array_merge()
#1 /usr/share/php/Composer/DependencyResolver/DefaultPolicy.php(84): call_user_func_array()
#2 /usr/share/php/Composer/DependencyResolver/Solver.php(387): Composer\DependencyResolver\DefaultPolicy->selectPreferredPackages()
#3 /usr/share/php/Composer/DependencyResolver/Solver.php(740): Composer\DependencyResolver\Solver->selectAndInstall()
#4 /usr/share/php/Composer/DependencyResolver/Solver.php(231): Composer\DependencyResolver\Solver->runSat()
#5 /usr/share/php/Composer/Installer.php(489): Composer\DependencyResolver\Solver->solve()
#6 /usr/share/php/Composer/Installer.php(232): Composer\Installer->doInstall()
#7 /usr/share/php/Composer/Command/UpdateCommand.php(163): Composer\Installer->run()
#8 /usr/share/php/Symfony/Component/Console/Command/Command.php(255): Composer\Command\UpdateCommand->execute()
#9 /usr/share/php/Symfony/Component/Console/Application.php(934): Symfony\Component\Console\Command\Command->run()
#10 /usr/share/php/Symfony/Component/Console/Application.php(273): Symfony\Component\Console\Application->doRunCommand()
#11 /usr/share/php/Composer/Console/Application.php(281): Symfony\Component\Console\Application->doRun()
#12 /usr/share/php/Symfony/Component/Console/Application.php(149): Composer\Console\Application->doRun()
#13 /usr/share/php/Composer/Console/Application.php(113): Symfony\Component\Console\Application->run()
#14 /usr/bin/composer(62): Composer\Console\Application->run()
#15 {main}
  thrown in /usr/share/php/Composer/DependencyResolver/DefaultPolicy.php on line 84
```

SOLUTION:

i have the same issue " Fatal error: **Uncaught ArgumentCountError: array_merge() does not accept unknown named parameters in /usr/share/php/Composer/DependencyResolver/DefaultPolicy.php:84** "
and everything is fine and working on my other Linux server. I search for so long on google and StackOverflow and try different solutions, but still the same error.

**Recommendation**: *just install the latest version of the composer in Linux and define it globally and run it on the project directory and the issue is resolved.*

Composer **1.10.1** ----> to ------> Composer version **2.3.4**

**Hint**: if same then revoke the composer.lock and vendor folder and run it again.

# TO INSTALL THE LATEST VERSION OF COMPOSER RUN THESE COMMMAND:

Step 1 — Install Dependencies
 ```
 sudo apt update
sudo apt install php-cli unzip
```
Step 2 — Download and Install Composer
Make sure you’re in your home directory, then retrieve the Composer installer using curl:
```
cd ~
curl -sS https://getcomposer.org/installer -o /tmp/composer-setup.php
```
Next, we’ll verify that the downloaded installer matches the SHA-384 hash for the latest installer found on the Composer Public Keys / Signatures page.

Using curl, fetch the latest signature and store it in a shell variable:
```
HASH=`curl -sS https://composer.github.io/installer.sig`
```
Now execute the following PHP code to verify that the installation script is safe to run:
```
php -r "if (hash_file('SHA384', '/tmp/composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
```
>Installer verified
>**Note:** If the output says Installer corrupt, you’ll need to repeat the download and verification process until you have a verified installer.

The following command will download and install Composer as a system-wide command named composer, under /usr/local/bin:
```
sudo php /tmp/composer-setup.php --install-dir=/usr/local/bin --filename=composer
```
To test your installation, run:
```
composer
```
# Output
 ```
   ______
  / ____/___  ____ ___  ____  ____  ________  _____
 / /   / __ \/ __ `__ \/ __ \/ __ \/ ___/ _ \/ ___/
/ /___/ /_/ / / / / / / /_/ / /_/ (__  )  __/ /
\____/\____/_/ /_/ /_/ .___/\____/____/\___/_/
                    /_/
Composer version 2.3.4 
```
>This verifies that Composer was successfully installed on your system and is available system-wide.
>
**uninstall php version 7.4/8.1 ubuntu 20.04** Code Example
```
sudo apt-get purge php7.*
sudo apt-get autoclean
sudo apt-get autoremove
```

[LINK] https://www.digitalocean.com/community/tutorials/how-to-install-composer-on-ubuntu-20-04-quickstart

[LINK] https://stackoverflow.com/questions/39337127/i-cannot-install-php-composer-in-ubuntu-16-04





  
