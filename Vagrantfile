

#
Vagrant.configure("2") do |config|
  config.vm.box = "opentable/win-2012r2-standard-amd64-nocm"
  config.vm.hostname = "ad.box"
  config.vm.network :private_network, ip: "192.168.0.30"
  config.winrm.transport = :plaintext
  config.winrm.basic_auth_only = true
  config.vm.provision "shell", path: "ConfigureRemotingForAnsible.ps1"
  config.vm.provision "shell", reboot: true
end


# Vagrant.configure("2") do |config|
#     config.vm.define "test" do |test|
#         test.vm.box = "eratiner/w2016x64vmX"
#         test.vm.network "private_network", ip: "192.168.10.24"
#         test.vm.hostname = "test"
#         test.vm.provision "shell", path: "ConfigureRemotingForAnsible.ps1"
#         test.vm.provision "shell", privileged: "true", powershell_elevated_interactive: "true", inline: <<-SHELL
#         Restart-Service -Name wuauserv –Force -Verbose
#         SHELL
#
#     end
# end


# test.vm.provision "shell", inline: <<-SHELL
#      Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
#      Set-TimeZone 'Eastern Standard Time'
# SHELL
