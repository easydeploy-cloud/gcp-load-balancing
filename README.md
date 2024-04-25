
# Load Balacing in GCP

## Startup Script for VM Instances

```bash
sudo apt-get update
sudo apt-get install apache2 -y
sudo a2ensite default-ssl
sudo a2enmod ssl
sudo service apache2 restart
echo '<!doctype html><html><body><h1>server 1</h1></body></html>' | sudo tee /var/www/html/index.html
```

## Firewall settings for SSH 

**Name:** ```allow-ssh-from-iap```

**Target tags:** ```http-tag```

**Source IP Ranges:** ```35.235.240.0/20```

**Allowed protocols and ports:** ```tcp:22```

## Firewall settings for HTTP 

**Name 🠊** ```allow-http-from-lb```

**Target tags 🠊** ```http-tag```

**Source IP Ranges 🠊** ```130.211.0.0/22``` and ```35.191.0.0/16``` .

**Allowed protocols and ports 🠊** ```tcp:22```
