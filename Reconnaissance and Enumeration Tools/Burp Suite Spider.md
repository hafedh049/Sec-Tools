 - **Purpose**: Automatically maps out the structure of a website.
   - **Usage**: Crawl a target web application to discover all links, parameters, and functionalities.
   - **Syntax Examples**:
     - GUI-based tool, typically initiated after intercepting traffic.
   - **When to Use**: Use the Burp Suite spider in the early stages of web application testing to map the web app's functionality and attack surface【14†source】.

Sure! Here’s a detailed breakdown of Burp Suite's Spider tool options, along with examples for each:

---

### **Burp Suite Spider Options**

1. **Scope Configuration:**
   - **Include in Scope:**
     - **Description:** Define which parts of the application are included in the spider’s crawl.
     - **Example:** If you want to include only the `/login` page and its subpages, you can add it to the scope. Set "Include in scope" to `http://example.com/login*`.

   - **Exclude from Scope:**
     - **Description:** Specify parts of the application that should be excluded from crawling.
     - **Example:** To exclude admin-related URLs, add `http://example.com/admin*` to the exclusion list.

2. **Spider Settings:**
   - **Follow Redirects:**
     - **Description:** Choose whether the spider should follow HTTP redirects.
     - **Example:** Set to "Yes" if you want the spider to follow redirects from `http://example.com/oldpage` to `http://example.com/newpage`.

   - **Request Rate:**
     - **Description:** Control the rate at which requests are sent during crawling.
     - **Example:** Set the request rate to 5 requests per second to avoid overwhelming the server.

   - **Max Crawl Depth:**
     - **Description:** Define the maximum depth of URLs to crawl from the starting point.
     - **Example:** Setting a crawl depth of 3 will limit the spider to crawling URLs up to 3 levels deep from the initial URL.

   - **Max Pages:**
     - **Description:** Limit the total number of pages the spider will crawl.
     - **Example:** Set to 500 pages to restrict the spider from crawling beyond 500 pages.

3. **Spider Options:**
   - **Use HTTP/HTTPS Protocol:**
     - **Description:** Specify whether to use HTTP or HTTPS for crawling.
     - **Example:** If your application uses HTTPS, ensure the spider is set to use HTTPS by checking "Use HTTPS".

   - **Include Files:**
     - **Description:** Decide whether to include or exclude non-HTML files (e.g., PDFs, images).
     - **Example:** Set to "Include" if you want to crawl URLs for PDFs located at `http://example.com/files/doc.pdf`.

   - **Include Parameters:**
     - **Description:** Choose whether to include URL parameters in the crawl.
     - **Example:** Enable this option if you want to crawl `http://example.com/page?id=123` and other parameterized URLs.

4. **Advanced Options:**
   - **User-Agent Header:**
     - **Description:** Specify a custom User-Agent string to use for the spider's requests.
     - **Example:** Set to "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3" to mimic a common browser.

   - **Authentication:**
     - **Description:** Configure authentication if the application requires login to access pages.
     - **Example:** Set up form-based authentication by entering the login URL, username, and password.

   - **Cookies:**
     - **Description:** Manage cookies that should be sent with requests during crawling.
     - **Example:** Add cookies like `session_id=abcd1234` if your application uses session-based authentication.

5. **Running and Monitoring:**
   - **Start Spidering:**
     - **Description:** Begin the spidering process.
     - **Example:** Click the "Spider" button to start crawling the URLs specified in your scope.

   - **Pause/Resume/Stop:**
     - **Description:** Control the spider’s execution.
     - **Example:** Click "Pause" to halt crawling temporarily, and "Resume" to continue from where it left off.

6. **Post-Spider Analysis:**
   - **Site Map:**
     - **Description:** View and analyze the URLs and structure discovered by the spider.
     - **Example:** The Site Map will show a hierarchical view of URLs such as `http://example.com/home`, `http://example.com/about`, etc.

   - **Issue Detection:**
     - **Description:** Identify potential vulnerabilities based on the spidered data.
     - **Example:** Use the spidered URLs to run scans for vulnerabilities like XSS, SQL Injection, etc.

---

This guide should help you configure and use the Burp Suite Spider tool effectively. If you have any specific questions or need further examples, let me know!