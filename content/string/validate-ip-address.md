# Validate IP Address

## 题目描述

Write a function to check whether an input string is a valid IPv4 address or IPv6 address or neither.

**IPv4**addresses are canonically represented in dot-decimal notation, which consists of four decimal numbers, each ranging from 0 to 255, separated by dots \("."\), e.g.,`172.16.254.1`;

Besides, leading zeros in the IPv4 is invalid. For example, the address`172.16.254.01`is invalid.

**IPv6**addresses are represented as eight groups of four hexadecimal digits, each group representing 16 bits. The groups are separated by colons \(":"\). For example, the address`2001:0db8:85a3:0000:0000:8a2e:0370:7334`is a valid one. Also, we could omit some leading zeros among four hexadecimal digits and some low-case characters in the address to upper-case ones, so`2001:db8:85a3:0:0:8A2E:0370:7334`is also a valid IPv6 address\(Omit leading zeros and using upper cases\).

However, we don't replace a consecutive group of zero value with a single empty group using two consecutive colons \(::\) to pursue simplicity. For example,`2001:0db8:85a3::8A2E:0370:7334`is an invalid IPv6 address.

Besides, extra leading zeros in the IPv6 is also invalid. For example, the address`02001:0db8:85a3:0000:0000:8a2e:0370:7334`is invalid.

**Note:**You may assume there is no extra space or special characters in the input string.

**Example 1:**

```text
Input:
 "172.16.254.1"


Output:
 "IPv4"


Explanation:
 This is a valid IPv4 address, return "IPv4".
```

**Example 2:**

```text
Input:
 "2001:0db8:85a3:0:0:8A2E:0370:7334"


Output:
 "IPv6"


Explanation:
 This is a valid IPv6 address, return "IPv6".
```

**Example 3:**

```text
Input:
 "256.256.256.256"


Output:
 "Neither"


Explanation:
 This is neither a IPv4 address nor a IPv6 address.
```

## 题目链接

[https://leetcode.com/problems/validate-ip-address/description/](https://leetcode.com/problems/validate-ip-address/description/)

## Java

根据题目的ipv4和ipv6的定义来判断是否是合法的。

```java
public class Solution {
    public String validIPAddress(String IP) {
        if (IP.matches(".*[.:]$|^[.:].*")) return "Neither";
        String[] ipv4Strs = IP.split("\\.");
        if (ipv4Strs.length == 4) {
            for (int i = 0; i < ipv4Strs.length; i++) {
                if (!ipv4Strs[i].matches("[0-9]*") || "".equals(ipv4Strs[i]) ||
                        ipv4Strs[i].length() > 3 || Integer.parseInt(ipv4Strs[i]) > 255 || (ipv4Strs[i].startsWith("0") && ipv4Strs[i].length() > 1))
                    return "Neither";
            }
            return "IPv4";
        }
        String[] ipv6Strs = IP.split(":");
        if (ipv6Strs.length == 8) {
            for (int i = 0; i < ipv6Strs.length; i++) {
                if (!ipv6Strs[i].matches("[0-9a-fA-F]*") || "".equals(ipv6Strs[i]) || ipv6Strs[i].length() > 4 || (ipv6Strs[i].matches(".*[A-F].*") && ipv6Strs[i].startsWith("0") && ipv6Strs[i].length() > 1))
                    return "Neither";
            }
            return "IPv6";
        }
        return "Neither";
    }
}
```

