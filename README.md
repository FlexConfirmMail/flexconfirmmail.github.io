# flexconfirmmail.github.io

URL: https://www.flexconfirmmail.com

## How to build the website locally

1. Install Sphinx, pydata-sphinx-theme, and sphinx-design (to use the dropdown feature)

   ```
   $ python3 -m pip install -U --user Sphinx pydata-sphinx-theme sphinx-design
   ```

2. Compile the source files using `make`.

   ```
   $ make html
   ```

3. The website should be available in `build/html`.

4. To check if root relative paths work, start http.server at `build/html`.

   ```
   $ python3 -m http.server 8000
   ```

   Then open `http://localhost:8000` on your browser.

   Change the port number if needed.
