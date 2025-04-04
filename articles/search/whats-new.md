---
title: What's new in Azure AI Search
description: Announcements of new and enhanced features, including a service rename of Azure Cognitive Search to Azure AI Search.

manager: nitinme
author: HeidiSteen
ms.author: heidist
ms.service: azure-ai-search
ms.topic: overview
ms.date: 02/28/2025
ms.custom:
  - references_regions
  - ignite-2024
---

# What's new in Azure AI Search

**Azure Cognitive Search is now Azure AI Search**. Learn about the latest updates to Azure AI Search functionality, docs, and samples.

> [!NOTE]
> Preview features are announced here, but we also maintain a [preview features list](search-api-preview.md) so you can find them in one place.

## February 2025

| Item&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Type |  Description |
|-----------------------------|------|--------------|
| [**Customer-managed keys support for Managed HSM**](search-security-manage-encryption-keys.md) | Security | Use either Azure Key Vault or Azure Key Vault Managed HSM (Hardware Security Module) to store customer-managed keys for extra encryption of sensitive content. |

## December 2024

| Item&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Type |  Description |
|-----------------------------|------|--------------|
| [**RAG chat with Azure AI Search + Python**](https://azure.github.io/ai-app-templates/repo/azure-samples/azure-search-openai-demo/) | Template | An AI application template for building a RAG solution using Azure AI Search and Python. |

## November 2024

| Item&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Type |  Description |
|-----------------------------|------|--------------|
| [**Network security perimeter**](search-security-network-security-perimeter.md) | Security | Join a search service to a [network security perimeter](/azure/private-link/network-security-perimeter-concepts) to control network access to your search service. The Azure portal and the Management REST APIs in the [2024-06-01-preview](/rest/api/searchmanagement/network-security-perimeter-configurations?view=rest-searchmanagement-2024-06-01-preview&preserve-view=true) can be used to view and reconcile network security perimeter configurations. |
| [**Shared private link support for Azure AI service connections**](search-indexer-howto-access-private.md) | Security  | Connections to Azure AI for built-in skills processing can now be private using a shared private link on the connection. |
| [**Rescoring options for compressed vectors**](/azure/search/vector-search-how-to-quantization?tabs=2024-11-01-preview%2Cquery-2024-07-01#add-compressions-to-a-search-index) | Relevance | You can set options to rescore with original vectors instead of compressed vectors. Applies to HNSW and exhaustive KNN vector algorithms, using binary and scalar compression. Available in the [Create or Update Index (2024-11-01-preview)](/rest/api/searchservice/indexes/create-or-update?view=rest-searchservice-2024-09-01-preview&preserve-view=true), the Azure portal, and in the Azure SDK beta packages that provide this feature. |
| [**Store fewer vector instances**](vector-search-how-to-storage-options.md) | vector search | In vector compression scenarios, you can omit storage of full precision vectors if you don't need them for rescoring. Available in the [Create or Update Index (2024-11-01-preview)](/rest/api/searchservice/indexes/create-or-update?view=rest-searchservice-2024-09-01-preview&preserve-view=true), the Azure portal, and in the Azure SDK beta packages that provide this feature. |
| [**Query rewrite in the semantic reranker**](semantic-how-to-query-rewrite.md) | Relevance | You can set options on a semantic query to rewrite the query input into a revised or expanded query that generates more relevant results from the L2 ranker. Available in the [Search Documents (2024-11-01-preview)](/rest/api/searchservice/documents/search-post?view=rest-searchservice-2024-11-01-preview&preserve-view=true), the Azure portal, and in the Azure SDK beta packages that provide this feature.|
| [**New semantic ranker models**](semantic-search-overview.md) | Relevance | Semantic ranker runs with improved models in all supported regions. There is no change to APIs or the Azure portal experience. |
| [**Document Layout skill**](cognitive-search-skill-document-intelligence-layout.md) | Applied AI (skills) | A new skill used to analyze a document for structure and provide [structure-aware (paragraph) chunking](search-how-to-semantic-chunking.md). This skill calls Document Intelligence and uses the Document Intelligence layout model. Available in selected regions through the [Create or Update Skillset (2024-11-01-preview)](/rest/api/searchservice/skillsets/create-or-update?view=rest-searchservice-2024-11-01-preview&preserve-view=true), the Azure portal, and in the Azure SDK beta packages that provide this feature.|
| [**Keyless billing for Azure AI skills processing**](cognitive-search-attach-cognitive-services.md) | Applied AI (skills) | You can now use a managed identity and roles for a keyless connection to Azure AI services for built-in skills processing. This capability removes restrictions for having both search and AI services in the same region. Available in the [Create or Update Skillset (2024-11-01-preview)](/rest/api/searchservice/skillsets/create-or-update?view=rest-searchservice-2024-11-01-preview&preserve-view=true), the Azure portal, and in the Azure SDK beta packages that provide this feature. |
| [**Markdown parsing mode**](search-how-to-index-markdown-blobs.md) | Indexer data source |  With this parsing mode, indexers can generate one-to-one or one-to-many search documents from Markdown files in Azure Storage and OneLake. Available in the [Create or Update Indexer (2024-11-01-preview)](/rest/api/searchservice/indexers/create-or-update?view=rest-searchservice-2024-11-01-preview&preserve-view=true), the Azure portal, and in the Azure SDK beta packages that provide this feature. |
| [**2024-11-01-preview**](/rest/api/searchservice/search-service-api-versions?view=rest-searchservice-2024-11-01-preview&preserve-view=true) | API | Preview release of REST APIs for query rewrite, Document Layout skill, keyless billing for skills processing, Markdown parsing mode, and rescoring options for compressed vectors. |
| [**Portal support for structured data**](search-get-started-portal-import-vectors.md) | Feature | The **Import and vectorize data** wizard now supports Azure SQL, Azure Cosmos DB, and Azure Table Storage.|

## October 2024

| Item&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Type |  Description |
|-----------------------------|------|--------------|
| [Lower the dimension requirements for MRL-trained text embedding models on Azure OpenAI](vector-search-how-to-truncate-dimensions.md) | Feature | Text-embedding-3-small and Text-embedding-3-large are trained using Matryoshka Representation Learning (MRL). This allows you to truncate the embedding vectors to fewer dimensions, and adjust the balance between vector index size usage and retrieval quality. A new `truncationDimension` in the [2024-09-01-preview](/rest/api/searchservice/indexes/create-or-update?view=rest-searchservice-2024-09-01-preview&preserve-view=true) enables access to MRL compression in text embedding models. This can only be configured for new vector fields. |
| [Unpack `@search.score` to view subscores in hybrid search results](hybrid-search-ranking.md#unpack-a-search-score-into-subscores-preview) | Feature | You can investigate Reciprocal Rank Fusion (RRF) ranked results by viewing the individual query subscores of the final merged and scored result. A new `debug` property unpacks the search score. `QueryResultDocumentSubscores`, `QueryResultDocumentRerankerInput`, and `QueryResultDocumentSemanticField` provide the extra detail. These definitions are available in the [2024-09-01-preview](/rest/api/searchservice/documents/search-post?view=rest-searchservice-2024-09-01-preview&preserve-view=true). |
| [Target filters in a hybrid search to just the vector queries](hybrid-search-how-to-query.md#hybrid-search-with-filters-targeting-vector-subqueries-preview) | Feature | A filter on a hybrid query involves all subqueries on the request, regardless of type. You can override the global filter to scope the filter to a specific subquery. The new `filterOverride` parameter is available on hybrid queries using the [2024-09-01-preview](/rest/api/searchservice/documents/search-post?view=rest-searchservice-2024-09-01-preview&preserve-view=true). |
| [Text Split skill (token chunking)](cognitive-search-skill-textsplit.md) | Applied AI (skills) | This skill has new parameters that improve data chunking for embedding models. A new `unit` parameter lets you specify token chunking. You can now chunk by token length, setting the length to a value that makes sense for your embedding model. You can also specify the tokenizer and any tokens that shouldn't be split during data chunking. The new `unit` parameter and query subscore definitions are found in the [2024-09-01-preview](/rest/api/searchservice/skillsets/create-or-update?view=rest-searchservice-2024-09-01-preview&preserve-view=true). |
| [2024-09-01-preview](/rest/api/searchservice/search-service-api-versions?view=rest-searchservice-2024-09-01-preview&preserve-view=true) | API | Preview release of REST APIs for truncated dimensions in text-embedding-3 models, targeted vector filtering for hybrid queries, RRF subscore details for debugging, and token chunking for Text Split skill.|
| [Portal support for customer-managed key encryption (CMK)](search-security-manage-encryption-keys.md#step-4-encrypt-content) | Feature | When you create new objects in the Azure portal, you can now specify CMK-encryption and select an Azure Key Vault to provide the key. |

## August 2024

| Item&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Type |  Description |
|-----------------------------|------|--------------|
| [Debug Session improvements](cognitive-search-debug-session.md) | feature | There are two important improvements. First, you can now debug integrated vectorization and data chunking workloads. Second, Debug Sessions is redesigned for a more streamlined presentation of skills and mappings. You can select an object in the flow, and view or edit its details in a side panel. The previous tabbed layout is fully replaced with more context-sensitive information on the page. |
| [2024-07-01](/rest/api/searchservice/search-service-api-versions?view=rest-searchservice-2024-07-01&preserve-view=true) | API | Stable release of REST APIs for generally available vector data types, vector compression, and integrated vectorization during indexing and queries. |
| [Integrated vectorization](vector-search-integrated-vectorization.md) | Feature | Announcing general availability. Skills-driven data chunking and embedding during indexing. |
| [Vectorizers](vector-search-how-to-configure-vectorizer.md) | Feature  | Announcing general availability. Text-to-vector conversion during query execution. Both [Azure OpenAI vectorizer](vector-search-vectorizer-azure-open-ai.md) and [custom Web API vectorizer](vector-search-vectorizer-custom-web-api.md) are generally available. |
| [AzureOpenAIEmbedding skill](cognitive-search-skill-azure-openai-embedding.md) | Feature | Announcing general availability. A skill type that calls an Azure OpenAI embedding model to generate embeddings during indexing.  |
| [Index projections](index-projections-concept-intro.md) | Feature | Announcing general availability. A component of a skillset definition that defines the shape of a secondary index, supporting a one-to-many index pattern, where content from an enrichment pipeline can target multiple indexes. |
| [Binary and Scalar quantization](vector-search-how-to-quantization.md)  | Feature | Announcing general availability. Compress vector index size in memory and on disk using built-in quantization. |
| [Narrow data types](vector-search-how-to-assign-narrow-data-types.md) | Feature  | Announcing general availability. Assign a smaller data type on vector fields, assuming incoming data is of that data type. |
| [Import and vectorize data wizard](search-get-started-portal-import-vectors.md) | Azure portal | Announcing general availability. A wizard that creates a full indexing pipeline that includes data chunking and vectorization. The wizard creates all necessary objects and configurations. This release adds wizard support for Azure Data Lake in Azure Storage.|
| [stored property](vector-search-how-to-storage-options.md) | Feature  | Announcing general availability. Boolean that reduces storage of vector indexes by *not* storing retrievable vectors. |
| [vectorQueries.Weight property](vector-search-how-to-query.md#vector-weighting) | Feature  | Announcing general availability. Specify the relative weight of each vector query in a search operation. |

## July 2024

| Item&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Type |  Description |
|-----------------------------|------|--------------|
| [Chat with your data](https://github.com/Azure-Samples/chat-with-your-data-solution-accelerator) | Accelerator| A solution accelerator for the RAG pattern running in Azure, using Azure AI Search for retrieval and Azure OpenAI large language models to create conversational search experiences. The code with sample data is available for use case scenarios such as financial advisor and contract review and summarization.|
| [Conversational Knowledge Mining](https://github.com/microsoft/Customer-Service-Conversational-Insights-with-Azure-OpenAI-Services) | Accelerator| A solution accelerator built on top of Azure AI Search, Azure Speech and Azure OpenAI services that allows customers to extract actionable insights from post-contact center conversations. |
| [Build your own copilot](https://github.com/microsoft/Build-your-own-AI-Assistant-Solution-Accelerator) | Accelerator| Create your own custom copilot solution that empowers [Client Advisor](https://github.com/microsoft/Build-your-own-copilot-Solution-Accelerator/blob/main/ClientAdvisor/README.md) to harness the power of generative AI across both structured and unstructured data. Help our customers to optimize daily tasks and foster better interactions with more clients.  |

## June 2024

| Item&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Type |  Description |
|-----------------------------|------|--------------|
| [Image search in the Azure portal](search-get-started-portal-image-search.md) | Feature | Search explorer now supports image search. In a vector index that has vectorized image content, you can drop images into Search Explorer to query for a match.

## May 2024

| Item&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Type |  Description |
|-----------------------------|------|--------------|
| [Higher capacity and more vector quota at every tier (same billing rate)](search-limits-quotas-capacity.md#service-limits) | Infrastructure | For most regions, partition sizes are now even larger for Standard 2 (S2), Standard 3 (S3), and Standard 3 High Density (S3 HD) for services created after April 3, 2024. To get the larger partitions, create a new service in a [region that provides newer infrastructure](search-region-support.md). <br><br>Storage Optimized tiers (L1 and L2) also have more capacity. L1 and L2 customers must create a new service to benefit from the higher capacity. There's no in-place upgrade at this time. <br><br>Extra capacity is now available in [more regions](search-limits-quotas-capacity.md#service-limits): Germany North​, Germany West Central​, South Africa North​, Switzerland West​, and Azure Government (Texas, Arizona, and Virginia).|
| [OneLake integration (preview)](search-how-to-index-onelake-files.md) | Feature | New indexer for OneLake files and OneLake shortcuts. If you use Microsoft Fabric and OneLake for data access to Amazon Web Services (AWS) and Google data sources, use this indexer to import external data into a search index. This indexer is available through the Azure portal, the [2024-05-01-preview REST API](/rest/api/searchservice/data-sources/create-or-update?view=rest-searchservice-2024-05-01-preview&preserve-view=true), and Azure SDK beta packages. |
| [Vector relevance](vector-search-how-to-query.md) <br>[hybrid query relevance](hybrid-search-how-to-query.md) | Feature | Four enhancements improve vector and hybrid search relevance. <br><br>First, you can now set thresholds on vector search results to exclude low-scoring results. <br><br>Second, changes in the query architecture apply scoring profiles at the end of the query pipeline for every query type. Document boosting is a common scoring profile, and it now works as expected on vector and hybrid queries.<br><br>Third, you can set [`MaxTextRecallSize` and `countAndFacetMode`](hybrid-search-how-to-query.md#set-maxtextrecallsize-and-countandfacetmode) in hybrid queries to control the quantity of BM25-ranked search results that flow into the hybrid ranking model. <br><br>Fourth, for vector and hybrid search, you can weight a vector query to have boost or diminish its importance in a multiquery request. |
| [Binary vectors support](/rest/api/searchservice/supported-data-types) | Feature | `Collection(Edm.Byte)` is a new supported data type. This data type opens up integration with the [Cohere v3 binary embedding models](https://cohere.com/blog/int8-binary-embeddings) and custom binary quantization. Narrow data types lower the cost of large vector datasets. See [Index binary data for vector search](vector-search-how-to-index-binary-data.md) for more information.| 
| [Azure AI Vision multimodal embeddings skill (preview)](cognitive-search-skill-vision-vectorize.md) | Skill | New skill that's bound to the [multimodal embeddings API of Azure AI Vision](/azure/ai-services/computer-vision/concept-image-retrieval). You can generate embeddings for text or images during indexing. This skill is available through the Azure portal and the [2024-05-01-preview REST API](/rest/api/searchservice/operation-groups?view=rest-searchservice-2024-05-01-preview&preserve-view=true).|
| [Azure AI Vision vectorizer (preview)](vector-search-vectorizer-ai-services-vision.md) | Vectorizer | New vectorizer connects to an Azure AI Vision resource using the [multimodal embeddings API](/azure/ai-services/computer-vision/concept-image-retrieval) to generate embeddings at query time. This vectorizer is available through the Azure portal and the [2024-05-01-preview REST API](/rest/api/searchservice/operation-groups?view=rest-searchservice-2024-05-01-preview&preserve-view=true). |
| [Azure AI Foundry model catalog vectorizer (preview)](vector-search-vectorizer-azure-machine-learning-ai-studio-catalog.md) | Vectorizer | New vectorizer connects to an embedding model deployed from the [Azure AI Foundry model catalog](/azure/ai-foundry/how-to/model-catalog-overview). This vectorizer is available through the Azure portal and the [2024-05-01-preview REST API](/rest/api/searchservice/operation-groups?view=rest-searchservice-2024-05-01-preview&preserve-view=true). <br><br>[**How to implement integrated vectorization using models from Azure AI Foundry**](vector-search-integrated-vectorization-ai-studio.md).|
| [AzureOpenAIEmbedding skill (preview) supports more models on Azure OpenAI](cognitive-search-skill-azure-openai-embedding.md) | Skill | Now supports text-embedding-3-large and text-embedding-3-small, along with text-embedding-ada-002 from the previous update. New `dimensions` and `modelName` properties make it possible to specify the various embedding models on Azure OpenAI. Previously, the dimensions limits were fixed at 1,536 dimensions, applicable to text-embedding-ada-002 only. The updated skill is available through the Azure portal and the [2024-05-01-preview REST API](/rest/api/searchservice/operation-groups?view=rest-searchservice-2024-05-01-preview&preserve-view=true).|
| Azure portal updates | Portal | [Import and vectorize data wizard](search-get-started-portal-import-vectors.md) now supports OneLake indexers as a data source. For embeddings, it also supports connections to Azure AI Vision multimodal, Azure AI Foundry model catalog, and more embedding models on Azure OpenAI. <br><br>When adding a field to an index, you can choose a [binary data type](vector-search-how-to-index-binary-data.md). <br><br>[Search explorer](search-explorer.md) now defaults to 2024-05-01-preview and supports the new preview features for vector and hybrid queries.  |
| [2024-05-01-preview](/rest/api/searchservice/search-service-api-versions#2024-05-01-preview) | API | New preview version of the Search REST APIs provides new skills and vectorizers, new binary data type, OneLake files indexer, and new query parameters for more relevant results. See [Upgrade REST APIs](search-api-migration.md) if you have existing code written against the 2023-07-01-preview and need to migrate to this version.|
| Azure SDK beta packages | API | Review the changelogs of the following Azure SDK beta packages for new feature support: [Azure SDK for Python](https://github.com/Azure/azure-sdk-for-python/blob/main/sdk/search/azure-search-documents/CHANGELOG.md), [Azure SDK for .NET](https://github.com/Azure/azure-sdk-for-net/blob/Azure.Search.Documents_11.6.0-beta.4/sdk/search/Azure.Search.Documents/CHANGELOG.md), [Azure SDK for Java](https://github.com/Azure/azure-sdk-for-java/blob/main/sdk/search/azure-search-documents/CHANGELOG.md) |
| [Python code samples](https://github.com/Azure/azure-search-vector-samples/blob/main/demo-python/readme.md)  | Samples | New end-to-end samples demonstrate [integration with Cohere Embed v3](https://github.com/Azure/azure-search-vector-samples/blob/main/demo-python/code/community-integration/cohere/azure-search-cohere-embed-v3-sample.ipynb), [integration with OneLake and cloud data platforms on Google and AWS](https://github.com/Azure/azure-search-vector-samples/blob/main/demo-python/code/e2e-demos/azure-ai-search-e2e-build-demo.ipynb), and [integration with Azure AI Vision multimodal APIs](https://github.com/Azure/azure-search-vector-samples/blob/main/demo-python/code/embeddings/multimodal-embeddings/multimodal-embeddings.ipynb). |

## April 2024

| Item&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Type |  Description |
|-----------------------------|------|--------------|
| [Security update addressing information disclosure](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2024-29063) | API | GET responses [no longer return connection strings or keys](search-api-migration.md#breaking-changes-for-client-code-that-reads-connection-information). Applies to GET Skillset, GET Index, and GET Indexer. This change helps protect your Azure assets integrated with AI Search from unauthorized access. |
| [More storage on Basic and Standard tiers](search-limits-quotas-capacity.md#service-limits) | Infrastructure |  Basic now supports up to three partitions and three replicas. Basic and Standard (S1, S2, S3) tiers have significantly more storage per partition, at the same per-partition billing rate. Extra capacity is subject to [regional availability](search-limits-quotas-capacity.md#service-limits) and applies to new search services created after April 3, 2024. Currently, there's no in-place upgrade, so you must create a new search service to get the extra storage. |
| [More quota for vectors](search-limits-quotas-capacity.md#vector-index-size-limits) | Infrastructure | Vector quotas are also higher on new services created after April 3, 2024 in selected regions. |
| [Vector quantization, narrow vector data types, and a new `stored` property (preview)](vector-search-how-to-configure-compression-storage.md) | Feature | Collectively, these three features add vector compression and smarter storage options. First, *scalar quantization* reduces vector index size in memory and on disk. Second, [narrow data types](/rest/api/searchservice/supported-data-types) reduce per-field storage by storing smaller values. Third, you can use `stored` to opt-out of storing the extra copy of a vector that's used only for search results. If you don't need vectors in a query response, you can set `stored` to false to save on space. |
| [2024-03-01-preview Search REST API](/rest/api/searchservice/search-service-api-versions#2024-03-01-preview) | API | New preview version of the Search REST APIs for the new data types, vector compression properties, and vector storage options. |
| [2024-03-01-preview Management REST API](/rest/api/searchmanagement/operation-groups?view=rest-searchmanagement-2024-03-01-preview&preserve-view=true) | API | New preview version of the Management REST APIs for control plane operations.  |
| [2023-07-01-preview deprecation announcement](/rest/api/searchservice/search-service-api-versions#2023-07-01-preview) | API | Deprecation announced on April 8, 2024. It becomes unsupported on July 8, 2024. This was the first REST API that offered vector search support. Newer API versions have a different vector configuration. You should [migrate to a newer version](search-api-migration.md) as soon as possible. |

## February 2024

| Item&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Type |  Description |
|-----------------------------|------|--------------|
| New dimension limits | Feature | For vector fields, maximum dimension limits are now `3072`, up from `2048`. |

## 2023 announcements

| Month | Type | Announcement |
|-------|------|-------------|
| November | Feature | [**Vector search, generally available**](vector-search-overview.md). The previous restriction on customer-managed keys (CMK) is now lifted. [Prefiltering](vector-search-how-to-query.md) and [exhaustive K-nearest neighbor algorithm](vector-search-ranking.md) are also now generally available. |
| November | Feature | [**Semantic ranker, generally available**](semantic-search-overview.md)|
| November | Feature | [**Integrated vectorization (preview)**](vector-search-integrated-vectorization.md) adds data chunking and text-to-vector conversions during indexing, and also adds text-to-vector conversions at query time. |
| November | Feature | [**Import and vectorize data wizard (preview)**](search-get-started-portal-import-vectors.md) automates data chunking and vectorization. It targets the [2023-10-01-Preview](/rest/api/searchservice/skillsets/create-or-update?view=rest-searchservice-2023-10-01-preview&preserve-view=true) REST API. | 
| November | Feature | [**Index projections (preview)**](index-projections-concept-intro.md) defines the shape of a secondary index, used for a one-to-many index pattern, where content from an enrichment pipeline can target multiple indexes. | 
| November | API | [**2023-11-01 Search REST API**](/rest/api/searchservice/search-service-api-versions#2023-11-01) is stable version of the Search REST APIs for [vector search](vector-search-overview.md) and [semantic ranking](semantic-how-to-query-request.md). See [Upgrade REST APIs](search-api-migration.md) for migration steps to generally available features.|
| November | API | [**2023-11-01 Management REST API**](/rest/api/searchmanagement/operation-groups?view=rest-searchmanagement-2023-11-01&preserve-view=true) adds APIs that [enable or disable semantic ranker](/rest/api/searchmanagement/services/create-or-update#searchsemanticsearch). |
| November | Skill | [**Azure OpenAI Embedding skill (preview)**](cognitive-search-skill-azure-openai-embedding.md) connects to a deployed embedding model on your Azure OpenAI resource to generate embeddings during skillset execution.|
| November | Skill | [**Text Split skill (preview)**](cognitive-search-skill-textsplit.md) updated in [2023-10-01-Preview](/rest/api/searchservice/skillsets/create-or-update?view=rest-searchservice-2023-10-01-preview&preserve-view=true) to support native data chunking. |
| November | Video | [**How vector search and semantic ranking improve your GPT prompts**](https://www.youtube.com/watch?v=Xwx1DJ0OqCk) explains how hybrid retrieval gives you optimal grounding data for generating useful AI responses and enables search over both concepts and keywords. |
| November | Sample | [**Role-based access control in Generative AI applications**](https://techcommunity.microsoft.com/t5/azure-ai-services-blog/access-control-in-generative-ai-applications-with-azure/ba-p/3956408) explains how to use Microsoft Entra ID and Microsoft Graph API to roll out granular user permissions on chunked content in your index. |
| October | Sample  | [**"Chat with your data" solution accelerator**](https://github.com/Azure-Samples/chat-with-your-data-solution-accelerator). End-to-end RAG pattern that uses Azure AI Search as a retriever. It provides indexing, data chunking, and orchestration. |
| October | Feature | [**Exhaustive  K-Nearest Neighbors (KNN)**](vector-search-overview.md#eknn) scoring algorithm for similarity search in vector space. Available in the 2023-10-01-Preview REST API only. |
| October | Feature | [**Prefilters in vector search**](vector-search-how-to-query.md) evaluate filter criteria before query execution, reducing the amount of content that needs to be searched. Available in the 2023-10-01-Preview REST API only, through a new `vectorFilterMode` property on the query that can be set to `preFilter` (default) or `postFilter`, depending on your requirements. |
| October | API | [**2023-10-01-Preview Search REST API**](/rest/api/searchservice/search-service-api-versions#2023-10-01-Preview), breaking changes the definition for [vector fields](vector-search-how-to-create-index.md) and [vector queries](vector-search-how-to-query.md).|
| August | Feature | [**Enhanced semantic ranking**](semantic-search-overview.md).  Upgraded models are rolling out for semantic reranking, and availability is extended to more regions. Maximum unique token counts doubled from 128 to 256.|
| July | Sample | [**Vector demo (Azure SDK for JavaScript)**](https://github.com/Azure/azure-search-vector-samples/blob/main/demo-javascript/readme.md). Uses Node.js and the **@azure/search-documents 12.0.0-beta.2** library to generate embeddings, create and load an index, and run several vector queries. |
| July | Sample | [**Vector demo (Azure SDK for .NET)**](https://github.com/Azure/azure-search-vector-samples/blob/main/demo-dotnet/DotNetVectorDemo/readme.md).  Uses the **Azure.Search.Documents 11.5.0-beta.3** library to generate embeddings, create and load an index, and run several vector queries. You can also try [this sample](https://github.com/Azure/azure-sdk-for-net/blob/main/sdk/search/Azure.Search.Documents/samples/Sample07_VectorSearch.md) from the Azure SDK team.|
| July | Sample | [**Vector demo (Azure SDK for Python)**](https://github.com/Azure/azure-search-vector-samples/tree/main/demo-python) Uses the latest beta release of the **azure.search.documents** to generate embeddings, create and load an index, and run several vector queries. Visit the [azure-search-vector-samples/demo-python](https://github.com/Azure/azure-search-vector-samples/blob/main/demo-python) repo for more vector search demos. |
| June | Feature | [**Vector search public preview**](vector-search-overview.md). |
| June | Feature | [**Semantic search availability**](semantic-search-overview.md), available on the Basic tier.|
| June | API | [**2023-07-01-Preview Search REST API**](/rest/api/searchservice/index-preview). Support for vector search. |
| May | Feature | [**Azure RBAC (role-based access control, generally available)**](search-security-rbac.md). |
| May | API | [**2022-09-01 Management REST API**](/rest/api/searchmanagement), with support for configuring search to use Azure roles. The **Az.Search** module of Azure PowerShell and **Az search** module of the Azure CLI are updated to support search service authentication options. You can also use the [**Terraform provider**](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/search_service) to configure authentication options (see this [Terraform quickstart](search-get-started-terraform.md) for details). | 
| April | Sample |  [**Multi-region deployment of Azure AI Search for business continuity and disaster recovery**](https://github.com/Azure-Samples/azure-search-multiple-regions). Deployment scripts that fully configure a multi-regional solution for Azure AI Search, with options for synchronizing content and request redirection if an endpoint fails. |
| March |  Sample | [**ChatGPT + Enterprise data with Azure OpenAI and Azure AI Search (GitHub)**](https://github.com/Azure-Samples/azure-search-openai-demo/blob/main/README.md). Python code and a template for combining Azure AI Search with the large language models in OpenAI. For background, see this Tech Community blog post: [Revolutionize your Enterprise Data with ChatGPT](https://techcommunity.microsoft.com/t5/ai-applied-ai-blog/revolutionize-your-enterprise-data-with-chatgpt-next-gen-apps-w/ba-p/3762087). <br><br>Key points: <br><br>Use Azure AI Search to consolidate and index searchable content.</br> <br>Query the index for initial search results.</br> <br>Assemble prompts from those results and send to the gpt-35-turbo (preview) model in Azure OpenAI.</br> <br>Return a cross-document answer and provide citations and transparency in your customer-facing app so that users can assess the response.</br> |

## Previous year's announcements

+ [2022 announcements](/previous-versions/azure/search/search-whats-new-2022)
+ [2021 announcements](/previous-versions/azure/search/search-whats-new-2021)
+ [2020 announcements](/previous-versions/azure/search/search-whats-new-2020)
+ [2019 announcements](/previous-versions/azure/search/search-whats-new-2019)

<a name="new-service-name"></a>

## Service rebrand

This service has had multiple names over the years. Here they are in reverse chronological order:

+ **Azure AI Search** (November 2023) Renamed to align with Azure AI services and customer expectations.
+ **Azure Cognitive Search** (October 2019) Renamed to reflect the expanded (yet optional) use of cognitive skills and AI processing in service operations.
+ **Azure Search** (March 2015) The original name.

## Service updates

[Service update announcements](https://azure.microsoft.com/updates/?product=search&status=all) for Azure AI Search can be found on the Azure web site.

## Feature rename

Semantic search was renamed to [semantic ranker](semantic-search-overview.md) in November 2023 to better describe the feature, which provides L2 ranking of an existing result set.
