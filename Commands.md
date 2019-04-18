# SCP file transfer command
<code>
scp -P 28604 -i ~/Downloads/id_rsa_braincloud -r /media/kevin/MyData/dataset/Spine/C-spine/C-spine_SNUBH root@csi-cluster-gpu1.cloud.kakaobrain.com:/data/private/

</code>

# Rename files
rename 's/string/string_you_want/' *

# The GPU id to use, usually either "0" or "1";
import os
os.environ["CUDA_DEVICE_ORDER"]="PCI_BUS_ID";
os.environ["CUDA_VISIBLE_DEVICES"]="0";  
 
