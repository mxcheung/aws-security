```
aws ec2 describe-security-groups \
    --query "SecurityGroups[?IpPermissionsEgress[?IpRanges[?CidrIp=='0.0.0.0/0'] && FromPort==0 && ToPort==65535]].GroupName" \
    --output text
```

```
aws ec2 describe-security-groups \
    --query "SecurityGroups[?IpPermissionsEgress[?IpRanges[?CidrIp=='0.0.0.0/0']] && IpPermissionsEgress[?FromPort=='-1' && ToPort=='-1']].GroupName" \
    --output text
```
```
aws ec2 describe-security-groups \
    --query "SecurityGroups[?IpPermissionsEgress[?IpRanges[?CidrIp=='0.0.0.0/0']] && IpPermissionsEgress[?FromPort=='-1' && ToPort=='-1']].GroupName" \
    --output text | tr '\t' '\n'

```
```
aws ec2 describe-security-groups \
    --query "SecurityGroups[?contains(GroupName, 'dt') && IpPermissionsEgress[?IpRanges[?CidrIp=='0.0.0.0/0']] && IpPermissionsEgress[?FromPort=='-1' && ToPort=='-1']].GroupName" \
    --output text | tr '\t' '\n'

```

```
Bad value for --query SecurityGroups[?IpPermissionsEgress[?IpRanges[?CidrIp=='0.0.0.0/0'] && FromPort==0 && ToPort==65535]].GroupName: invalid token: Parse error at column 81, token "0" (NUMBER), for expression:
"SecurityGroups[?IpPermissionsEgress[?IpRanges[?CidrIp=='0.0.0.0/0'] && FromPort==0 && ToPort==65535]].GroupName"
```
