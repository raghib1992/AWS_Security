# Lab Instructions - How to Create KeyPair for EC2


### Amazon Linux EC2 instances do not use user id and passwords as they are generally easy to guess

### Instead, they are protected using keypairs that you specify when launching the instance

### Keypair consists of a public key, which is like a user id and a private key, which is similar to a password

### So, when launching an instance, we need to specify the public key

###And when you log in, we need to present the matching private key and EC2 logs you in

* Steps - Keypair
    1. Login to AWS console using your myadmin user

    2. Open EC2 service console

    3. Make sure you don’t have any popup blockers for this site

    4. Ensure you are in the correct region – I am using US West Oregon. The keypair that we create are region-specific

    5. Select Key Pairs from the left navigation pane

    6. You can create a new one or import your existing key

    7. Let’s quickly look at the import option

    8. Action and Import Key pair

        a. You need to provide only the public key of your existing key pair

        b. This option is useful if you want to use the same key across different regions

        c. You can use tools like openssh or putty to generate your own keys

    https://www.ssh.com/academy/ssh/keygen

    9. The other option is we can ask AWS to create one for us

    10. Create Key Pair

        a. Name: my_ore_keypair

        I generally specify the username followed by region

        b. KeyPairType: RSA

        c. Private Key Format: Choose PPK format if you use a windows laptop. This format is compatible with the Putty tool that we will use on Windows. If you are on Mac or Linux laptop, you can select the PEM format. This format is compatible with the openssh tool

        d. I will select PPK format as I primarily work on Windows Laptop

        e. Using Putty tool, it is also possible to convert one format to another https://aws.amazon.com/premiumsupport/knowledge-center/ec2-ppk-pem-conversion/



    11. Create Keypair

    12. The page will automatically download the keypair to your machine. This is the only opportunity to download the keypair. EC2 will store only the corresponding public key in the console

    13. Keep this file in a safe location. Treat it like a user id and password. [For example, C:\AWSTraining\Labs]

    14. For Linux and Mac users, I will provide an article to follow

    15. We can now use the key pair to log in to EC2 instances

* Steps – Putty Tool
1. If you are on windows, please install the Putty Tool

2. Go to https://www.putty.org/

3. Download Putty

4. Download 64-bit x86 MSI

5. Install the app

## `Summary`
### In this short lab, we created a keypair and installed putty tool

### This is good to get started on windows.

### If you are on Linux or Mac – please follow these instructions

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html