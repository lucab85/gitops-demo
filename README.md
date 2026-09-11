# M3L3 — GitOps Repo Walkthrough

Questa cartella riproduce il repository `gitops-demo` dello script: una base condivisa, due overlay Kustomize e una Application Argo CD.

## Verifica locale

```bash
kubectl kustomize environments/development
kubectl kustomize environments/production
```

## Cambio mostrato nella screenshare

Aggiungere alla fine di `environments/development/kustomization.yaml`:

```yaml
images:
  - name: nginx
    newTag: 1.28-alpine
```

Prima di applicare `argocd/development.yaml`, sostituire `repoURL` con l'URL reale del repository pubblicato. In Argo CD mostrare la sequenza `Synced/Healthy` → `OutOfSync` → diff → Sync → `Synced/Healthy`.
# gitops-demo
