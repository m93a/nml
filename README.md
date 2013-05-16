# x2
HTML6-like Markup Language

## Procedure of data processing
1. Check if document is tag-valid
 * If not, throw an error
2. Parse x2 document
3. Get document's json-x2-rules
4. Check if document is type-valid, according to rules
 * If not, throw an error/warning
5. Get document's CSS
6. Apply CSS
7. Render
