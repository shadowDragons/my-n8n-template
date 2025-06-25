Deep web scrapper + RAG: Automation recursively downloads each page of the target website and extracts links, emails, texts, and PDF documents.
Then, all extracted data goes into RAG, from which you can later extract data via chat or any other interface.
Steps to follow:

1. Create a Supabase account and project.
2. Connect Supabase to n8n.
3. Connect PostgreSQL from Supabase to n8n.
4. Create Supabase tables and functions.
5. Run the automation.
6. If automation times out, you can re-run it with a click-to-start workflow node connected to the 'Check Supabase' node.
7. Sometimes, an HTTP request fails and causes automation to mark the URL as failed, but you can re-activate these URLs (after automation is finished) with another sub-flow. Then simply re-run the main web-scrapper automation.
