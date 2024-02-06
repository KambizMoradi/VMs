require 'yaml'
vagrant_default_provider=ENV['VAGRANT_DEFAULT_PROVIDER']
vars = YAML.load_file("vars.yaml")

Vagrant.configure(vars.fetch('vagrant_api_version')) do |config|
  config.vm.provider vagrant_default_provider do |vb|
    vb.default_prefix = vars["vagrant_default_prefix"]
  end

  vars["VMS"].each do |server|
    (1..server["count"]).each do |i|
      config.vm.define "#{server["prefix"]}#{i}" do |node|
        node.vm.box = server["box"]
        node.vm.hostname = "#{server["prefix"]}#{i}"
        node.vm.provider vagrant_default_provider do |vb|
          vb.cpus = server["cpu"]
          vb.memory = server["ram"]
        end
      end
    end
  end
end

