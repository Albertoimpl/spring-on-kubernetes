


*   If you run `$ skaffold dev --port-forward` everything should deploy as normal
```execute-1
skaffold dev --port-forward
```

*   Check that the ConfigMap was generated
```execute-2
kubectl get configmap
```
* You should see something similar to this

```
NAME                             DATA   AGE
k8s-demo-app-config-fcc4c2fmcd   1      18s

```

*   Skaffold is watching our files for changes, go ahead and change `logging.level.org.springframework` from `INFO` to `DEBUG` and Skaffold will automatically create a new ConfigMap and restart the pod
*   You should see a lot more logging in your terminal once the new pod starts

Be sure to kill the `skaffold` process before continuing

```terminal:interrupt
session: 1
```

---