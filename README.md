# dnsmasq hack session

> Set up dnsmasq with 3 virtual machines

- 192.168.2.101 foo.example.com
- 192.168.2.102 bar.example.com
- 192.168.2.103 baz.example.com

## Usage

```
git clone https://github.com/mbigras/dnsmasq-hack-session
cd dnsmasq-hack-session
vagrant up
vagrant status
ansible all -m ping
ansible-playbook main.yml
```

## Issue a lookup for baz.example.com from bar

```
vagrant ssh bar -c 'dig +short baz.example.com'
```

## Issue a request to application running on baz from bar

```
vagrant ssh bar -c 'curl baz.example.com:3000'
```
