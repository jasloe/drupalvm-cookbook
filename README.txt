#### Dependencies
ansible (2.2.2.0)
vagrant-auto_network (1.0.2)
vagrant-aws (0.7.2)
vagrant-bindfs (1.0.9)
vagrant-cachier (1.2.1)
vagrant-hostsupdater (1.0.2)
vagrant-share (1.1.7)
vagrant-vbguest (0.14.2)

#### Create a new Drupal project using drupal-project
<pre>
composer create-project drupal-composer/drupal-project:8.x-dev [projectname] --stability dev --no-interaction
</pre>

#### Require contribs
<pre>
composer require drupal/admin_toolbar:^1.0\
drupal/config_update:^1.3 drupal/deploy:1.0-beta1\
drupal/features:^3.5\ 
drupal/token:^1.0\
drupal/libraries:^3.0\
drupal/paragraphs:^1.0\
drupal/entity:^1.0-alpha4\
drupal/search_api:^1.0\
drupal/search_api_solr_multilingual:^1.0-beta3\
drupal/migrate_tools:4.0-beta1\
drupal/migrate_plus:4.0-beta1\
drupal/toolbar_anti_flicker:^2.6\
&& composer require --dev drupal/devel:^1.0
</pre>

#### From project root, add DrupalVM
<pre>
composer require --dev geerlingguy/drupal-vm
</pre>

#### and create a vm directory to host configuration files
<pre>



