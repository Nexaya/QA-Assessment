#### **C (`automation/c/README.md`):**

```markdown
# C Automation Instructions

## Task:
- Write an automated test script using **C** to test the login functionality of a web-based application.

## Requirements:
- You can use a framework like **libcurl** to perform HTTP requests or any other preferred C framework.
- Ensure to include assertions for success and failure scenarios.

## Deliverables:
- Submit your C code along with instructions to compile and run the test.

---

## Sample:
```c
#include <stdio.h>
#include <curl/curl.h>

int main() {
    CURL *curl;
    CURLcode res;

    curl = curl_easy_init();
    if(curl) {
        curl_easy_setopt(curl, CURLOPT_URL, "http://example.com/login");
        curl_easy_setopt(curl, CURLOPT_POSTFIELDS, "username=valid_username&password=valid_password");

        res = curl_easy_perform(curl);
        if(res != CURLE_OK) {
            fprintf(stderr, "curl_easy_perform() failed: %s\n", curl_easy_strerror(res));
        }

        curl_easy_cleanup(curl);
    }
    return 0;
}
