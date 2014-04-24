docker-sshd-centos
==================

A Dockerfile to build a sshd service with supervisord on latest CentOS Container

# Installation

- paste your public key to `authorized_keys`
```sh
cat ~/.ssh/id_rsa.pub >> authorized_keys
```

- Build
```sh
docker build --no-cache --rm -t local/centos .
```

- RUN container
```sh
ID=$(docker run -i -t -d -p 22 local/centos)
```

- Login to your container
```sh
ssh localhost -p `docker port $ID 22 | cut -d":" -f2`
```

Root password is `root`

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
