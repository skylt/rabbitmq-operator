# rabbitmq-operator

## Purpose

This operator was made to remove the need to have credentials written down in
manifests.
It achieves this by generating the credentials and storing them in a secret
during the creation process.

## Configuration

- `deploy/operator`:
    Set the correct image name
- `deploy/role_binding.yaml`:
    Set the namespace where the operator will be deployed

## Deploying
```shellsession
NAMESPACE="kube-system"
kubectl -n $NAMESPACE apply -Rf deploy/
```
To deploy a simple rabbitmq service:
```shellsession
NAMESPACE="test-rabbitmq"
kubectl -n $NAMESPACE apply -Rf cr/simple.yaml
watch -n1 kubectl -n $NAMESPACE get pods
```

## Usage example

A further example, showing how to connect and send a simple message to the
rabbitmq instance may be found [here](https://github.com/skylt/rabbitmq-example).
