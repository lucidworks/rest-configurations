# REST V2 Connector Recipes

This repository contains ready-to-use recipes for the [Fusion REST V2 connector](https://doc.lucidworks.com/docs/fusion-connectors/connectors/rest-v2/overview) — a single connector that can index content from any REST API-compatible datasource.

Each recipe is a preconfigured JSON file for a specific datasource, with the endpoints, pagination, and field mappings already set up. Load a recipe into Fusion, fill in your credentials and connection details, and start crawling.

> You must install the REST V2 connector in Fusion before using these recipes.

## Available recipes

| Datasource | Recipe | Documentation |
| --- | --- | --- |
| Alfresco | [`alfresco/alfresco.json`](alfresco/alfresco.json) | [alfresco.asciidoc](alfresco/alfresco.asciidoc) |
| Confluence | [`confluence/confluence.json`](confluence/confluence.json) | [confluence.asciidoc](confluence/confluence.asciidoc) |
| GitHub | [`github/github-repo.json`](github/github-repo.json) | [github.asciidoc](github/github.asciidoc) |
| Jira | [`jira/jira.json`](jira/jira.json) | [jira.asciidoc](jira/jira.asciidoc) |

## Using a recipe

1. Open the recipe's JSON file and copy its contents.
2. Replace the placeholders in the JSON with your own values — at minimum, `serviceURL`, authentication credentials, `collection`, and `pipeline`.
3. Send it to Fusion as the body of a POST request to the [Connector Datasources API](https://doc.lucidworks.com/api-reference/datasource-configuration-v2-api/create-a-v2-datasource):

   ```bash
   curl --location --request POST 'https://FUSION_HOST/api/apps/APP_NAME/connectors/datasources' \
   --header 'Content-Type: application/json' \
   --header 'Authorization: Basic AUTHORIZATION_CREDENTIALS=' \
   --data-raw '{JSON_RECIPE}'
   ```

4. In Fusion, go to **Indexing > Datasources**, find the new datasource, and review or adjust the configuration.
5. Save and run the datasource to start crawling.

For a full walkthrough of each JSON field and how to adapt a recipe to your setup, see [Recipes](https://doc.lucidworks.com/docs/fusion-connectors/connectors/rest-v2/recipes/overview) and the [REST V2 connector reference](https://doc.lucidworks.com/docs/fusion-connectors/connectors/rest-v2/overview) on the Lucidworks documentation site.
