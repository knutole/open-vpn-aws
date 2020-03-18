# open-vpn-aws
Setup instructions for open-vpn

# Guide
Use this guide: https://medium.com/@tatianaensslin/how-to-create-a-free-personal-vpn-in-the-cloud-using-ec2-openvpn-626c40e96dab, with additions below.

# Additions

## Use smallest instance
`t2.nano` is sufficient, 8GB disk as well.

## Create dedicated VPC
1. Create a VPC
2. Add a subnet (10.0.0.0/32 for example)
3. Add elastic IP
4. Create Internet Gateway for VPC
5. IMPORTANT: Ensure there's a ROUTE to the Internet Gateway: 0.0.0.0/0 -> the IG (target)

## Username
1. You can use the `openvpn` user, but you need to create a new password: `sudo passwd openvpn`. Make it 30+ chars. This is the username you'll log with on your OpenVPN client.
