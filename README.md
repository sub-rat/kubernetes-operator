
# Kuberneted Operator

## steps followed to create the operator
## 1. Create boilerplate of project 
```operator-sdk new presentation-operator --type go --repo github.com/NautiluX/presentation-example-operator```

## 2. Generate api code  
```operator-sdk add api --kind Presentation --api-version presentation.subratgyawai.com.np/v1alpha1```

<br>
After changing the spec in presentation_type.go

## 3. Genereate actual CRD(Custom Resource Defination) and go codes
```operator-sdk generate crds```
```operator-sdk generate k8s```

## 4. Deploy CRD
```kubectl apply -f deploy/crds/presentation.subratgyawai.com.np_presentations_crd.yaml```

## 5. Create Controller of operator to handle CR
```operator-sdk add controller --kind Presentation --api-version presentation.subratgyawali.com.np/v1alpha1```

## 6. Run locally 
```operator-sdk run --local```