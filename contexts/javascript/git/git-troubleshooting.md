# Git troubleshooting

### index.lock

If a message like `... index.lock ... file exists ...` appears then run this command: 

```text
$ rm -f .git/index.lock
```

This should reset the local repo :\)

{% hint style="success" %}
I recommend having a look at the humorous but useful site [https://ohshitgit.com/](https://ohshitgit.com/) for the most common Git problems and how to solve them!
{% endhint %}

