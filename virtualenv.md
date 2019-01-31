# 1.Make account:

You need ubuntu acoount first. For sudoers information, please contact administrator.

    sudo adduser $yourname
        
And please fill out your information.

# 2.How to install virtualenv in my account:
 
Firstly, log in with your account

    virtualenv -p python3 $yourname 

You can choose python2 also

# Active your virtual environment:
 
    source $yourname/bin/activate
    
# To deactivate:
  
    deactivate
