# lancement d'une machine alpine 
$vagrant init generic/alpine38
$vagrant up
-modicfication de nom du machine et du memoireRAM:
$ vb.memory = "1024"
$ vb.name = "alpine-test1"
-installation du apache2 par un script:
 $config.vm.provision "shell", inline: <<-SHELL
    $ apk update
     $apk add apache2
     $rc-service apache2 start
    $SHELL
-installation du apache2 par un lien de fichier: on creer un fichier script.sh sous rep courant
$config.vm.provision "shell", path: "script.sh"
-le contenu du script.sh est: 
apk update
apk add apache2
rc-service apache2 start

#lancer 2 machines dans un meme vagrantfile par un seul vagrant up: 
web et db


