# KAI frontend Kubernetes manifests

The UI ships as the container image **`iahmedsabry/kai-frontend`** (see `deployment.yaml`). Static files and nginx routing live in the **`ai-ops-platform`** repo under `frontend/` (Dockerfile + `npm run build`). CI builds and pushes the image; **Argo CD** syncs this folder from the GitOps repo (`path: manifests/core-apps/kai-frontend`).

Legacy **`frontend-html`** / **`frontend-nginx-config`** ConfigMaps are removed; HTML is baked into the image.
