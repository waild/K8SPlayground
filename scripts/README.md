# K8SPlayground
K8SPlayground

##Using a plugin
### To use a plugin, make the plugin executable:
```bash
sudo chmod +x ./kubectl-kubeplugin
```
### and place it anywhere in your PATH:
```bash
sudo cp ./kubeplugin /usr/local/bin/kubectl-kubeplugin
```
### You may now invoke your plugin as a kubectl command:
```bash
kubectl kubeplugin kube-system
```