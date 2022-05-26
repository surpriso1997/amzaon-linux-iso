### Steps:

1. Download the vdi(for oracle virtual box) or ova(for vmware) file from aws's the link below.

   [Run Amazon linux 2 on prem](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/amazon-linux-2-virtual-machine.html)

   [Download Vm image from here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/amazon-linux-2-virtual-machine.html#amazon-linux-2-virtual-machine-download)

2. Rename the `user-data.example` file to user-data

3. Replace your own ssh-public key and passoword in the user-data file:

```yaml
users:
  - default
  - name: ec2-user
    ssh-authorized-keys:
      - your-ssh-public-key
```

```yaml
chpasswd:
  list: |
    ec2-user:your-password
```

> Make sure there is o space between ec2-user: and the actual password.

4. Run

```
chmod +x gen_iso.sh
./gen_iso.sh
```
