# **Question**

![[Networking_mcqs.pdf]]


# **Answers**

Here are the solutions and explanations for the multiple-choice questions provided in the PDF.

---

### **IPv4 Fundamentals**

1. An IPv4 address consists of __________ bits. 1

**Answer**: C) 32 2

Explanation: An IPv4 address is a 32-bit number, typically written as four octets (e.g., 192.168.1.1).

2. In IPv4, class __________ has the greatest number of addresses in each block. 3

**Answer**: A) A 4

**Explanation**: Class A networks use 24 bits for the host portion, allowing for 224 (over 16 million) addresses per network block, which is the largest of any class. 5

3. Identify the class of the following IPv4 address: 4.5.6.7. 6

**Answer**: A) A 7

Explanation: The first octet, 4, falls within the Class A range of 1-126.

4. Identify the class of the following IPv4 address: 229.1.2.3. 8

**Answer**: C) D 9

Explanation: The first octet, 229, falls within the Class D (multicast) range of 224-239.

5. Identify the class of the following IPv4 address: 191.1.2.3. 10

**Answer**: B) B 11

Explanation: The first octet, 191, falls within the Class B range of 128-191.

---

### **Bitwise AND Operations**

6. What is the result of ANDing 255 and 15? 12

**Answer**: B) 15 13

Explanation: 255 is 11111111 in binary and 15 is 00001111. A bitwise AND results in 00001111, which is 15.

7. What is the result of ANDing 0 and 15? 14

**Answer**: C) 0 15

Explanation: 0 is 00000000 in binary. ANDing any number with 0 will always result in 0.

8. What is the result of ANDing 254 and 15? 16

**Answer**: B) 14 17

Explanation: 254 is 11111110 in binary and 15 is 00001111. A bitwise AND results in 00001110, which is 14.

9. What is the result of ANDing 192 and 65? 18

**Answer**: C) 64 19

Explanation: 192 is 11000000 in binary and 65 is 01000001. A bitwise AND results in 01000000, which is 64.

---

### **IPv4 Addressing and Subnetting**

10. Which one is not a contiguous mask? 20

**Answer**: C) 255.148.0.0 21

Explanation: A valid subnet mask must have a continuous series of ones followed by a continuous series of zeros in its binary representation. 148 in binary is 10010100, which has zeros mixed in with the ones, making it non-contiguous.

11. The number of addresses in a class C block is __________. 22

**Answer**: C) 256 23

Explanation: A Class C block uses 8 bits for the host portion, which allows for 28=256 total addresses.

12. The number of addresses in a class B block is __________. 24

**Answer**: A) 65,536 25

Explanation: A Class B block uses 16 bits for the host portion, allowing for 216=65,536 total addresses.

13. The number of addresses in a class A block is __________. 26

**Answer**: B) 16,777,216 27

Explanation: A Class A block uses 24 bits for the host portion, allowing for 224=16,777,216 total addresses.

14. The number of addresses assigned to an organization in classless addressing __________. 28

**Answer**: C) must be a power of 2 29

Explanation: In classless addressing (CIDR), the block size is determined by the number of host bits, so it must always be a power of 2 (e.g., 2, 4, 8, 16, 32...).

15. The first address assigned to an organization in classless addressing __________. 30

**Answer**: B) must be evenly divisible by the number of addresses 31

Explanation: This is a fundamental rule of CIDR block allocation. For example, a block of 32 addresses must start on an address that is a multiple of 32 (e.g., 0, 32, 64...).

16. Which address could be the beginning address of a block of 32 classless addresses? 32

**Answer**: C) 2.4.6.64 33

Explanation: The starting address must be evenly divisible by the block size (32). Of the options, only 64 is divisible by 32.

17. Which address could be the beginning address of a block of 16 classless addresses? 34

**Answer**: D) none of the above 35

**Explanation**: The starting address must be evenly divisible by 16. None of the options (5, 15, 62) are divisible by 16. 36

18. Which address could be the beginning address of a block of 256 classless addresses? 37

**Answer**: C) 2.4.6.0 38

Explanation: A block of 256 addresses means the entire last octet is used for hosts. Therefore, the starting address must have a 0 in the last octet.

19. What is the first address of a block of classless addresses if one of the addresses is 12.2.2.76/27? 39

**Answer**: C) 12.2.2.64 40

Explanation: A /27 prefix means the block size is 2(32−27)=25=32. The multiples of 32 are 0, 32, 64, 96... The address 76 falls into the block that starts at 64.

20. What is the first address of a block of classless addresses if one of the addresses is 12.2.2.76/10? 41

**Answer**: A) 12.0.0.0 42

Explanation: A /10 mask means the first 10 bits are for the network. The IP address 12.2.2.76 in binary starts with 00001100.00000010.... The first 10 bits are 00001100.00. Setting all host bits to zero gives 00001100.00000000.00000000.00000000, which is 12.0.0.0.

21. What is the first address of a block of classless addresses if one of the addresses is 12.2.2.127/28? 43

**Answer**: C) 12.2.2.112 44

Explanation: A /28 prefix means the block size is 2(32−28)=24=16. The multiples of 16 are ..., 96, 112, 128... The address 127 falls into the block that starts at 112.

22. Find the number of addresses in a block of classless addresses if one of the addresses is 12.2.2.7/24. 45

**Answer**: C) 256 46

Explanation: A /24 prefix leaves 32−24=8 bits for the host portion. The number of addresses is 28=256.

23. Find the number of addresses in a block of classless addresses if one of the addresses is 12.2.2.7/30. 47

**Answer**: B) 4 48

Explanation: A /30 prefix leaves 32−30=2 bits for the host portion. The number of addresses is 22=4.

24. What is the last address of a block of classless addresses if one of the addresses is 12.2.2.127/28? 49

**Answer**: C) 12.2.2.127 50

Explanation: From question 21, the block starts at 12.2.2.112 and has 16 addresses. The next block starts at 12.2.2.128. Therefore, the last address in this block is 12.2.2.127.

25. What is the last address of a block of classless addresses if one of the addresses is 12.2.2.6/30? 51

**Answer**: C) 12.2.2.7 52

Explanation: A /30 prefix has a block size of 4. The block containing address 6 starts at 12.2.2.4. The next block starts at 12.2.2.8. The last address in this block is therefore 12.2.2.7.

26. An organization is granted a block; one address is 2.2.2.64/20. The organization needs 10 subnets. What is the subnet prefix length? 53

**Answer**: B) /24 54

Explanation: To create 10 subnets, you must borrow enough bits to satisfy the requirement. 23=8 subnets (not enough). 24=16 subnets (enough). You need to borrow 4 bits. The new prefix length is the original prefix plus the borrowed bits: 20+4=24.

27. An organization is granted a block; one address is 2.2.2.64/25. If the subnet prefix length is /28, what is the maximum number of subnets? 55

**Answer**: C) 8 56

Explanation: The number of bits borrowed for subnetting is the difference between the new prefix and the original prefix: 28−25=3 bits. The maximum number of subnets is 23=8.

28. An organization is granted a block of classless addresses with the starting address 199.34.76.64/28. How many addresses are granted? 57

**Answer**: B) 16 58

Explanation: A /28 prefix leaves 32−28=4 bits for hosts. The number of addresses is 24=16.

29. An organization is granted a block of classless addresses with the starting address 199.34.76.128/29. How many addresses are granted? 59

**Answer**: A) 8 60

Explanation: A /29 prefix leaves 32−29=3 bits for hosts. The number of addresses is 23=8.

30. An organization is granted a block of classless addresses with the starting address 199.34.32.0/27. How many addresses are granted? 61

**Answer**: C) 32 62

Explanation: A /27 prefix leaves 32−27=5 bits for hosts. The number of addresses is 25=32.

---

### **CIDR and Masks**

31. What is the default mask for class A in CIDR notation? 63

**Answer**: B) /8 64

Explanation: Class A networks use the first 8 bits to identify the network.

32. What is the default mask for class B in CIDR notation? 65

**Answer**: C) /16 66

Explanation: Class B networks use the first 16 bits to identify the network.

33. What is the default mask for class C in CIDR notation? 67

**Answer**: A) /24 68

Explanation: Class C networks use the first 24 bits to identify the network.

34. In classless addressing, the __________ is another name for the common part of the address range. 69696969

**Answer**: B) prefix 70

Explanation: The "prefix" is the portion of the address that is common to all addresses in a given network block (e.g., 192.168.1.0/24).

35. In classless addressing, the __________ is the varying part (similar to the hostid). 71

**Answer**: A) suffix 72

Explanation: The "suffix" is the part of the address that varies to identify individual hosts within the network block.

36. In classless addressing, the prefix length defines the __________. 73

**Answer**: C) mask 74

Explanation: The prefix length (e.g., /24) is a shorthand way of representing the subnet mask.

37. In a block, the prefix length is /24; what is the mask? 75

**Answer**: A) 255.255.255.0 76

Explanation: A /24 prefix means the first 24 bits are ones, which translates to 255.255.255.0 in dotted-decimal notation.

38. In a block, the prefix length is /15; what is the mask? 77

**Answer**: A) 255.254.0.0 78

Explanation: A /15 prefix in binary is 11111111.11111110.00000000.00000000. The second octet, 11111110, is 254 in decimal.

39. In a block, the mask is 255.255.192.0; what is the prefix length? 79

**Answer**: C) /18 80

Explanation: 255 is 8 bits, 255 is 8 bits, and 192 (11000000) is 2 bits. The total number of network bits (the prefix length) is 8+8+2=18.

---

### **IPv6 Fundamentals**

40. An IPv6 address is __________ bits long. 81

**Answer**: C) 128 82

Explanation: IPv6 addresses were expanded to 128 bits to provide a vastly larger address space than IPv4.

41. An IPv6 address consists of __________ bytes (octets). 83838383

**Answer**: C) 16 84

Explanation: An IPv6 address is 128 bits long, and since there are 8 bits in a byte, the address consists of 128/8=16 bytes.

42. To make addresses more readable, IPv6 specifies __________ notation. 85

**Answer**: B) hexadecimal colon 86

Explanation: IPv6 addresses are written using hexadecimal numbers separated by colons (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334).

43. In hexadecimal colon notation, a 128-bit address is divided into __________ sections, each __________ hexadecimal digits in length. 878787878787878787

Answer: C) 8; 4 88

Explanation: An IPv6 address is composed of 8 sections (or hextets), with each section containing 4 hexadecimal digits.

44. An IPv6 address can have up to __________ colons. 89898989

**Answer**: B) 7 90

Explanation: There are 8 sections in an IPv6 address, which are separated by 7 colons.

45. An IPv6 address can have up to __________ hexadecimal digits. 91919191

**Answer**: B) 32 92

Explanation: With 8 sections and 4 hexadecimal digits per section, the total number of digits is 8×4=32.

46. In IPv6, __________ address defines a single computer. 93

**Answer**: A) a unicast 94

Explanation: A unicast address is used for one-to-one communication and uniquely identifies a single network interface.

47. In IPv6, __________ address defines a group of computers with addresses that have the same prefix. 95

**Answer**: C) an anycast 96

Explanation: An anycast address is assigned to a group of interfaces. A packet sent to an anycast address is delivered to just one of those interfaces, typically the one that is geographically closest to the source.

48. In IPv6, __________ address defines a group of computers. 97

**Answer**: B) a multicast 98

Explanation: A multicast address is used for one-to-many communication. A packet sent to a multicast address is delivered to all interfaces that have joined that multicast group.

49. In IPv6, the __________ prefix defines the purpose of the address. 99999999

**Answer**: A) type 100

Explanation: The initial bits of an IPv6 address form a "type prefix" that identifies the address's purpose (e.g., global unicast, link-local, multicast).

50. In IPv6, the __________ address is generally used by a normal host as a unicast address. 101

**Answer**: A) provider-based unicast 102

Explanation: This is an older term for what is now called a Global Unicast Address (GUA). It is the standard, globally unique, and routable address assigned to a host.

51. In IPv6, a __________ address comprises 80 bits of zero, followed by 16 bits of one, followed by the 32-bit IPv4 address. 103

**Answer**: C) mapped 104

Explanation: This describes an IPv4-mapped IPv6 address (e.g., ::ffff:192.0.2.1), which is used to represent an IPv4 address within the IPv6 architecture.

52. In IPv6, a __________ address is an address of 96 bits of zero followed by 32 bits of IPv4 address. 105

**Answer**: D) none of the above 106

Explanation: This describes an IPv4-compatible IPv6 address, which is a deprecated format. None of the given options (link local, site local, mapped) are correct. 107

53. In IPv6, a __________ address is used if a LAN uses the Internet protocols but is not connected to the Internet for security reasons. 108

**Answer**: A) link local 109

Explanation: Link-local addresses (prefix FE80::/10) are used for communication between devices on the same single network link and are not routable.

54. In IPv6, a __________ address is used if a site with several networks uses the Internet protocols but is not connected to the Internet for security reasons. 110

**Answer**: B) site local 111

Explanation: Site-local addresses (prefix FEC0::/10) were designed for use within a single site or organization without needing a globally unique prefix. This address type is now deprecated and replaced by Unique Local Addresses (ULA).