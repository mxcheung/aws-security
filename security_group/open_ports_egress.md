```
aws ec2 describe-security-groups \
    --query "SecurityGroups[?IpPermissionsEgress[?IpRanges[?CidrIp=='0.0.0.0/0'] && FromPort==0 && ToPort==65535]].GroupName" \
    --output text
```
