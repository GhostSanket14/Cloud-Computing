# Cloud-Computing
This contain code for EC2 cloud computing
AWS EC2 is a popular way to manage and launch virtual machines. Here is a fast way to launch a code-server machine with AWS EC2:

Log into AWS and head over to the EC2 dashboard. Launch a new instance.

Use the "Ubuntu Server 20.04 LTS" 64-bit (x86) Quick Start.

Choose t2.micro instance type or larger.

Click Next: Configure Instance Details to add the code-server script.

Under User data, copy & paste the launch-code-server.sh script.

Expand your storage, if necessary under the "Add Storage" section.

Under "Security Groups," ensure you have rows for "SSH" (:22) and "HTTP" (:80)

Add any SSH keys, if necessary, and launch the instance.

Once your instance starts, you can simply navigate to the public IP address and get forwarded to a secure version of code-server, which will be proxied behind your GitHub account (the first one you log in with). For information on how this works, see code-server --link.

Optional: To change the URL in the address bar from ip-[xxxx] to something more descriptive, you just need to change your hostname and restart code-server:

sudo hostnamectl set-hostname bens-devbox
sudo systemctl restart code-server@coder
