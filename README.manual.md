# 1. Procedure to open incident, so that it will show at https://weezevent.github.io/status-page/

## 1.1 Manual:

1. Create Github Issue
2. Set any title for Github Issue you wish to show at the page https://weezevent.github.io/status-page/
3. set labels `status` and label for name of service like it is added in .upptimerc.yml, but all in lowcase and having replaced spaces with `-`. Example: for name: `if i break with spaces` you need to add label `what-if-i-break-with-spaces`

## 1.2 Automated:

1. you can break service on purpose by adding impossible condition seeing status code 601 for example. Also it will open Github Issue automatically with correctly assigned labels

```yaml
name: What if i break with spaces
url: https://duckduck.go
expectedStatusCodes:
 - 601

```

P.S. This action can be done in addition to manually opened Github Issue

# 2. Procedure to close incident:

## 2.1 Automated

1. If it was opened through status code 601, then remove next lines from .upptimerc.yml in the necessary service

```yml
expectedStatusCodes:
- 601
```

## 2.2 Manual

3. If Github Issue was opened manually, then just close it manually

# Notes

P.S. Optionally trigger `Uptiime CI` to update github pages web site quicker any performed action
