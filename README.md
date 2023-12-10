 97 Tests for Authentication API


1. Basic credentials:
```json
{"login": "admin",
"password": "admin"}
```

2. Empty credentials:
```json
{"login": "",
"password": ""}
```

3. Null values:
```json
{"login": null,
"password": null}
```

4. Credentials as numbers:
```json
{"login": 123,
"password": 456}
```

5. Credentials as booleans:
```json
{"login": true,
"password": false}
```


6. Credentials as arrays:
```json
{"login": ["admin"],
"password": ["password"]}
```


7. Credentials as objects:
```json
{"login": {"username": "admin",
"password": {"password": "password"}
}}
```


8. Special characters in credentials:
```json
{"login": "@dm!n",
"password": "p@ssw0rd#"}
```

9. SQL Injection:
```json
{"login": "admin' --",
"password": "password"}
```

10. HTML tags in credentials:
```json
{"login": "<h1>admin</h1>",
"password": "ololo-HTML-XSS"}
```

11. Unicode in credentials:
```json
{"login": "\u0061\u0064\u006D\u0069\u006E",
"password":"\u0070\u0061\u0073\u0073\u0077\u006F\u0072\u0064"}
```

12. Credentials with escape characters:
```json
{"login": "ad\\nmin",
"password": "pa\\ssword"}
```

13. Credentials with white space:
```json
{"login": " ",
"password": " "}
```

14. Overlong values:
```json
{"login": "a"*10000,
"password": "b"*10000}
```

15. Malformed JSON (missing brace):
```json
{"login": "admin",
"password": "admin"}
```

16. Malformed JSON (extra comma):
```json
{"login": "admin",
"password": "admin",}
```


17. Missing login key:
```json
{"password": "admin"}
```

18. Missing password key:
```json
{"login": "admin"}
```

19. Swapped key values:
```json
{"admin": "login",
"password": "password"}
```

20. Extra keys:
```json
{"login": "admin",
"password": "admin",
"extra": "extra"}
```

21. Missing colon:
```json
{"login" "admin",
"password": "password"}
```

22. Invalid Boolean as credentials:
```json
{"login": yes,
"password": no}
```



23. All keys, no values:
```json
{"": "",
"": ""}
```

24. Nested objects:
```json
{"login": {"innerLogin": "admin",
"password": {"innerPassword": "password"}}}
```

25. Case sensitivity testing:
```json
{"LOGIN": "admin",
"PASSWORD": "password"}
```

26. Login as a number, password as a string:
```json
{"login": 1234,
"password": "password"}
```

27. Login as a string, password as a number:
```json
{"login": "admin",
"password": 1234}
```


28. Repeated keys:
```json
{"login": "admin",
"login": "user",
"password": "password"}
```

29. Single quotes instead of double:
```json
{'login': 'admin',
'password': 'password'}
```

30. Login and password with only special characters:
```json
{"login": "@#$%^&*",
"password": "!@#$%^&*"}
```

31. Unicode escape sequence:
```json
{"login": "\u0041\u0044\u004D\u0049\u004E",
"password":"\u0050\u0041\u0053\u0053\u0057\u004F\u0052\u0044"}
```

32. Value as object instead of string:
```json
{"login": {"$oid":"507c7f79bcf86cd7994f6c0e"},
"password": "password"}}
```


33. Nonexistent variables as values:
```json
{"login": undefined,
"password": undefined}
```


34. Extra nested objects:
```json
{"login": "admin",
"password": "password","extra": {"key1": "value1","key2": "value2"}}
```


35. Hexadecimal values:
```json
{"login": "0x1234",
"password": "0x5678"}
```

36. Extra symbols after valid JSON:
```json
{"login": "admin",
"password": "password"}@@@@@@}
```


37. Only keys, without values:
```json
{"login":,
"password":}
```


38. Insertion of control characters:
```json
{"login": "ad\u0000min",
"password": "pass\u0000word"}
```

39. Long Unicode Strings:
```json
{"login": "\u0061"*10000,
"password": "\u0061"*10000}
```



40. Newline Characters in Strings:
```json
{"login": "ad\nmin",
"password": "pa\nssword"}
```

41. Tab Characters in Strings:
```json
{"login": "ad\tmin",
"password": "pa\tssword"}
```

42. Test with HTML content in Strings:
```json
{"login": "<b>admin",
"password": "password"}
```

43. JSON Injection in Strings:
```json
{"login": "{\"injection\":\"value\"}",
"password": "password"}
```

44. Test with XML content in Strings:
```json
{"login": "admin",
"password": "password"}
```

45. Combination of Number, Strings, and Special characters:
```json
{"login": "ad123min!@",
"password": "pa55w0rd!@"}
```

46. Floating numbers as Strings:
```json
{"login": "123.456",
"password": "789.123"}
```

47. Value as a combination of languages (Here, English and
Hindi):
```json
{"login": "adminà¤µà¥à¤¯à¤µà¤¸à¥à¤¥à¤¾à¤ªà¤•",
"password": "passwordà¤ªà¤¾à¤¸à¤µà¤°à¥à¤¡"}
```

48. Non-ASCII characters in Strings:
```json
{"login": "âˆ†adminâˆ†",
"password": "âˆ†passwordâˆ†"}
```

49. Single Character Keys and Values:
```json
{"l": "a",
"p": "p"}
```

50. Use of environment variables:
```json
{"login": "${USER}",
"password": "${PASS}"}
```

51. Backslashes in Strings:
```json
{"login": "ad\\min",
"password": "pa\\ssword"}
```

52. Long strings of special characters:
```json
{"login": "!@#$%^&*()"*1000,
"password": "!@#$%^&*()"*1000}
```



53. Empty Key in JSON:
```json
{"": "admin",
"password": "password"}
```

54. JSON Injection in Key:
```json
{"{\"injection\":\"value\"}": "admin",
"password": "password"}
```

55. Quotation marks in strings:
```json
{"login": "\"admin\"",
"password": "\"password\""}
```

56. Credentials as nested arrays:
```json
{"login": [["admin"]],
"password": [["password"]]}
```



57. Credentials as nested objects:
```json
{"login": {"username": {"value": "admin",
"password": {"password": {"value":"password"}
```

58. Keys as numbers:
```json
{123: "admin",
456: "password"}
```

59. Testing with greater than and less than signs:
```json
{"login": "admin>1",
"password": "<password"}
```

60. Testing with parentheses in credentials:
```json
{"login": "(admin)",
"password": "(password)"}
```

61. Credentials containing slashes:
```json
{"login": "admin/user",
"password": "pass/word"}
```

62. Credentials containing multiple data types:
```json
{"login": ["admin",123,true,null,{"username": ["admin"],
"password": ["password",123,false,null,{"password": "password"]}}}
```



63. Using escape sequences:
```json
{"login": "admin\\r\\n\\t",
"password": "password\\r\\n\\t"}
```

64. Using curly braces in strings:
```json
{"login": "{admin}",
"password": "{password}"}
```

65. Using square brackets in strings:
```json
{"login": "[admin]",
"password": "[password]"}
```

66. Strings with only special characters:
```json
{"login": "!@#$$%^&*()",
"password": "!@#$$%^&*()"}
```

67. Strings with control characters:
```json
{"login": "admin\b\f\n\r\t\v\0",
"password": "password\b\f\n\r\t\v\0"}
```

68. Null characters in strings:
```json
{"login": "admin\0",
"password": "password\0"}
```

69. Exponential numbers as strings:
```json
{"login": "1e5",
"password": "1e10"}
```

70. Hexadecimal numbers as strings:
```json
{"login": "0xabc",
"password": "0x123"}
```

71. Leading zeros in numeric strings:
```json
{"login": "000123",
"password": "000456"}
```

72. Multilingual input (here, English and Korean):
```json
{"login": "adminê´€ë¦¬ìž",
"password": "passwordë¹„ë°€ë²ˆí˜¸"}
```

73. Extremely long keys:
```json
{"a"*10000: "admin",
"b"*10000: "password"}
```

74. Extremely long unicode strings:
```json
{"login": "\u0061"*10000,
"password": "\u0062"*10000}
```


75. JSON strings with semicolon:
```json
{"login": "admin;",
"password": "password;"}
```

76. JSON strings with backticks:
```json
{"login": "`admin`",
"password": "`password`"}
```

77. JSON strings with plus sign:
```json
{"login": "admin+",
"password": "password+"}
```

78. JSON strings with equal sign:
```json
{"login": "admin=",
"password": "password="}
```

79. Strings with Asterisk (*) Symbol:
```json
{"login": "admin*",
"password": "password*"}
```

80. JSON containing JavaScript code:
```json
{"login": "admin<script>alert('hi')</script>",
"password": "password"}
```

81. Negative numbers as strings:
```json
{"login": "-123",
"password": "-456"}
```

82. Values as URLs:
```json
{"login": "https://admin.com",
"password": "https://password.com"}
```

83. Strings with email format:
```json
{"login": "admin@admin.com",
"password": "password@password.com"}
```

84. Strings with IP address format:
```json
{"login": "192.0.2.0",
"password": "203.0.113.0"}
```

85. Strings with date format:
```json
{"login": "2023-08-03",
"password": "2023-08-04"}
```

86. JSON with exponential values:
```json
{"login": 1e+30,
"password": 1e+30}
```


87. JSON with negative exponential values:
```json
{"login": -1e+30,
"password": -1e+30}
```

88. Using Zero Width Space (U+200B) in strings:
```json
{"login": "adminâ€‹",
"password": "passwordâ€‹"}
```

89. Using Zero Width Joiner (U+200D) in strings:
```json
{"login": "adminâ€",
"password": "passwordâ€"}
```

90. JSON with extremely large numbers:
```json
{"login": 12345678901234567890,
"password": 12345678901234567890}
```


91. Strings with backspace characters:
```json
{"login": "admin\b",
"password": "password\b"}
```

92. Test with emoji in strings:
```json
{"login": "adminðŸ˜€",
"password": "passwordðŸ˜€"}
```

93. JSON with comments, although they are not officially supported in JSON:
```json
{/*"login": "admin",
"password": "password"*/}
```


94. JSON with base64 encoded values:
```json
{"login": "YWRtaW4=",
"password": "cGFzc3dvcmQ="}
```

95. Including null byte character (may cause truncation):
```json
{"login": "admin\0",
"password": "password\0"}
```

96. JSON with credentials in scientific notation:
```json
{"login": 1e100,
"password": 1e100}
```


97. Strings with octal values:
```json
{"login": "\141\144\155\151\156",
"password":"\160\141\163\163\167\157\162\144"}
```

## acknowledgment
special thanks to [wallarm](https://www.linkedin.com/company/wallarm/)