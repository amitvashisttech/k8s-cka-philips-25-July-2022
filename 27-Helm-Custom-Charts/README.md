```
 1456  mkdir 27-Helm-Custom-Charts
 1458  cd 27-Helm-Custom-Charts/
 1462  helm create mychart
 1464  cd mychart/
 1467  cat Chart.yaml
 1468  ls
 1469  cd charts/
 1470  ls
 1471  cd ..
 1472  ls
 1473  cat values.yaml
 1475  cat  templates/deployment.yaml
 1479  vim values.yaml
 1480  vim templates/deployment.yaml
 1486  helm install my-webapp mychart --dry-run
 1486  helm install my-webapp mychart 
