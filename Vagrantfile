Vagrant::Config.run do |config|
  config.vm.box = "precise32"

   config.vm.provision :chef_solo do |chef|
     chef.json = {
       'rbenv' => {
         'global' => '1.9.3-p194',
         'rubies' => [ '1.9.3-p194' ],
         'gems'   => {
            '1.9.3-p194' => [{ 'name'   => 'bundler' }]
          }
        }
     }
     chef.cookbooks_path = "cookbooks"
     chef.roles_path = "roles"
     
     chef.add_recipe 'apt::update'
     chef.add_role 'ruby'
   end
end
