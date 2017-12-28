This is a quick-and-dirty summary of tasks for building a local development virtual machine with the latest stable Drupal release, its dependencies, and a few contributed modules. It is intended to be used as the basis for a future suite of ArchivesSpace-Drupal integration modules, though could be used for really any purpose. 

- [ ] Include vm configuration file as an extra instead of requiring user to clone from another /jasloe/vm.git
- [ ] Add Java task runner for use by Islandora and Search API Solr
- [ ] Expose memory and CPU settings in config.yml
- [ ] Add documentation on building a remote staging box on EC2 using prod.config.yml

#### Dependencies
<pre>
ansible (2.2.1.0)
vagrant (>=1.9.4)
vagrant-auto_network (1.0.2)
vagrant-aws (0.7.2)
vagrant-bindfs (1.0.9)
vagrant-cachier (1.2.1)
vagrant-hostsupdater (1.0.2)
vagrant-share (1.1.7)
vagrant-vbguest (0.14.2)
</pre>

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

#### and create a vm directory to host configuration files and move drupal/vm/Vagranfile to drupal/Vagrantfile
<pre>
git clone https://github.com/jasloe/vm.git
</pre>

#### 

#### Modify config.yml
<pre>
drupal_site_name: "something"

drupal_enable_modules:
  - admin_toolbar
  - admin_toolbar_tools
  - config_update
  - features
  - features_ui
  - search_api
  - search_api_solr_multilingual
  - toolbar_anti_flicker
  - views
  - views_ui
</pre>

#### Modify vagrant.config.yml
<pre>
vagrant_hostname: local.drupal.local
vagrant_machine_name: local-drupal
</pre>