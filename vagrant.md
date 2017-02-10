
# vagrant(1)

Boxes

  Boxes are downloaded into `~/.vagrant.d/boxes`

    vagrant box add \<name> \<box>   # remote box
    vagrant box remove \<name>      # remove a box (delete)
    vagrant box list

Start VM

    vagrant init \<name>            # crates a Vagrantfile
    vagrant up                     # start environment

    vagrant suspend                # suspend a virtual machine (save state to disk)
    vagrant resume                 # resume a suspended virtual machine
    vagrant destroy                # shutdown the environment

Login

    vagrant ssh                    # login (no username/password needed, exit with ctrl-d)
    vagrant ssh -- -l thomd        # ssh into machine as user thomd
