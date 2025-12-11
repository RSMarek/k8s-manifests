# Kustomize
## Create configuration
```bash
mkdir -p nginx-01/kustomize/base
mkdir -p nginx-01/kustomize/overlays/dev

# base
cd nginx-01/kustomize/base
kustomize create --autodetect --recursive

# overlays
cd ..
cd overlays/dev
kustomize create --namespace dev --namesuffix "-dev" --resources '../../base'
```

## Render
```bash
cd ../../../../
kustomize build nginx-01/kustomize/overlays/dev/
```