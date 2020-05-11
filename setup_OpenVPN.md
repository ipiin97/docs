# Authentication (easy-rsa)
##### 1. (Linux) Clone the OpenVPN easy-rsa repo to your local computer and navigate to the easy-rsa/easyrsa3 folder
    git clone https://github.com/OpenVPN/easy-rsa.git
    cd easy-rsa/easyrsa3
##### 2. Initialize a new PKI environment
    ./easyrsa init-pki
##### 3. Build a new certificate authority (CA)
    ./easyrsa build-ca nopass
##### 4. Generate the server certificate and key
    ./easyrsa build-server-full server nopass
##### 5. Generate the client certificate and key
    ./easyrsa build-client-full client1.domain.tld nopass

##### 6. Copy the server certificate and key and the client certificate and key to a custom folder and then navigate into the custom folder
    mkdir ~/openvpn_auth/
    cp pki/ca.crt ~/openvpn_auth/
    cp pki/issued/server.crt ~/openvpn_auth/
    cp pki/private/server.key ~/openvpn_auth/
    cp pki/issued/client1.domain.tld.crt ~/openvpn_auth/
    cp pki/private/client1.domain.tld.key ~/openvpn_auth/
    cd ~/openvpn_auth/