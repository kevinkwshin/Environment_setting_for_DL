## 1.Make account:

You need ubuntu acoount first. For sudoers information, please contact administrator.

    sudo adduser $yourname
        
And please fill out your information.

## 2.How to install virtualenv in my account:
 
Firstly, log in with your account

    virtualenv -p python3 $yourname 

You can choose python2 also

## 3.Active your virtual environment:
 
    source $yourname/bin/activate

## 4.Enjoy Your virtualenv:
  
  You can download anything you want here.
  However, you need to save dataset into external drive which is /mnt/XXX

## 5.To deactivate:
  
    deactivate
