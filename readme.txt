# build kite-vm
vagrant up
# package kite-vm
vagrant package --vagrantfile Vagrantfile.box --output kite-vm.box
# publish kite-vm
vagrant cloud publish --force einfachIT/kite-vm <VERSION> virtualbox kite-vm.box 

