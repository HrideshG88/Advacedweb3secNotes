#Description: How to write goof reports

# GENERAL INFO

## Title

\<ROOT CAUSE> + \<IMPACT>

## Severity

LikelyHood x Impact

## Relevant Links

links to vuln code in repo

# BODY

## Summary

Brief. To The Point.

## Details

```lang
CODE {
    code
@>  vuln line
    code
}
```

code snippet with finding lines marked
exact details.

### POC

Steps to exploit.
better have **coded test/exploit** to prove validity of finding

## Imapact

Exactly how bad it is.

## Recommendations

Provide how it can be mitigated

```diff
- vuln removed
+ secure code added
```
