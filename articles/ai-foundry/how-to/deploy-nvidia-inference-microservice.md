---
title: How to deploy NVIDIA Inference Microservices
titleSuffix: Azure AI Foundry
description: Learn to deploy NVIDIA Inference Microservices, using Azure AI Foundry.
manager: scottpolly
ms.service: azure-ai-foundry
ms.topic: how-to
ms.date: 03/19/2025
ms.author: ssalgado
author: ssalgadodev
ms.reviewer: tinaem
reviewer: tinaem
ms.custom:  devx-track-azurecli
---

# How to deploy NVIDIA Inference Microservices

In this article, you learn how to deploy NVIDIA Inference Microservices (NIMs) on Managed Compute in the model catalog on Foundry​. NVIDIA inference microservices are containers built by NVIDIA for optimized pre-trained and customized AI models serving on NVIDIA GPUs​. 
Get increased throughput and reduced total cost ownership with NVIDIA NIMs offered for one-click deployment on Foundry, with enterprise production-grade software under NVIDIA AI Enterprise license. 

[!INCLUDE [models-preview](../includes/models-preview.md)]

## Prerequisites

- An Azure subscription with a valid payment method. Free or trial Azure subscriptions won't work. If you don't have an Azure subscription, create a [paid Azure account](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go) to begin.

- An [Azure AI Foundry hub](create-azure-ai-resource.md).

- An [Azure AI Foundry project](create-projects.md).

- Ensure Marketplace purchases are enabled for your Azure subscription. Learn more about it [here](/azure/cost-management-billing/manage/enable-marketplace-purchases).

- Azure role-based access controls (Azure RBAC) are used to grant access to operations in Azure AI Foundry portal. To perform the steps in this article, your user account must be assigned a _custom role_ with the following permissions. User accounts assigned the _Owner_ or _Contributor_ role for the Azure subscription can also create NIM deployments. For more information on permissions, see [Role-based access control in Azure AI Foundry portal](../concepts/rbac-ai-foundry.md).

    -	On the Azure subscription—**to subscribe the workspace to the Azure Marketplace offering**, once for each workspace/project:
        -	Microsoft.MarketplaceOrdering/agreements/offers/plans/read
        -	Microsoft.MarketplaceOrdering/agreements/offers/plans/sign/action
        -	Microsoft.MarketplaceOrdering/offerTypes/publishers/offers/plans/agreements/read
        -	Microsoft.Marketplace/offerTypes/publishers/offers/plans/agreements/read
        -	Microsoft.SaaS/register/action

    -	On the resource group—**to create and use the SaaS resource**:
        -   Microsoft.SaaS/resources/read
        -	Microsoft.SaaS/resources/write

    -	On the workspace—**to deploy endpoints**:
        -	Microsoft.MachineLearningServices/workspaces/marketplaceModelSubscriptions/*
        -	Microsoft.MachineLearningServices/workspaces/onlineEndpoints/* 


## NVIDIA NIM PayGo offer on Azure Marketplace by NVIDIA

 NVIDIA NIMs available on Azure AI Foundry model catalog can be deployed with a subscription to the [NVIDIA NIM SaaS offer](https://aka.ms/nvidia-nims-plan) on Azure Marketplace. This offer includes a 90-day trial that applies to all NIMs associated with a particular SaaS subscription scoped to an Azure AI Foundry project, and has a PayGo price of $1 per GPU hour post the trial period. 

 Azure AI Foundry enables a seamless purchase flow of the NVIDIA NIM offering on Marketplace from NVIDIA collection in the model catalog, and further deployment on managed compute.

## Deploy NVIDIA Inference Microservices on Managed Compute

1. Sign in to [Azure AI Foundry](https://ai.azure.com) and go to the **Home** page.
2. Select **Model catalog** from the left sidebar.
3. In the filters section, select **Collections** and select **NVIDIA**.

:::image type="content" source="../media/how-to/deploy-nvidia-inference-microservice/nvidia-collections.png" alt-text="A screenshot showing the Nvidia inference microservices available in the model catalog." lightbox="../media/how-to/deploy-nvidia-inference-microservice/nvidia-collections.png":::  

4. Select the NVIDIA NIM of your choice. In this article, we are using **Llama-3.3-70B-Instruct-NIM-microservice** as an example.
5. Select **Deploy**.
6. Select one of the NVIDIA GPU based VM SKUs supported for the NIM, based on your intended workload. You need to have quota in your Azure subscription.
7. You can then customize your deployment configuration for the instance count, select an existing endpoint or create a new one, etc. For the example in this article, we consider an instance count of **1** and create a new endpoint. 

:::image type="content" source="../media/how-to/deploy-nvidia-inference-microservice/project-customization.png" alt-text="A screenshot showing project customization options in the deployment wizard." lightbox="../media/how-to/deploy-nvidia-inference-microservice/project-customization.png"::: 

8. Select **Next**
9. Then, review the pricing breakdown for the NIM deployment, terms of use and license agreement associated with the NIM offer. The pricing breakdown helps inform what the aggregated pricing for the NIM software deployed would be, which is a function of the number of NVIDIA GPUs in the VM instance that was selected in the previous steps. In addition to the applicable NIM software price, Azure Compute charges also applies based on your deployment configuration.

:::image type="content" source="../media/how-to/deploy-nvidia-inference-microservice/payment-description.png" alt-text="A screenshot showing the necessary user payment agreement detailing how the user is charged for deploying the models." lightbox="../media/how-to/deploy-nvidia-inference-microservice/payment-description.png":::  

10. Select the checkbox to acknowledge understanding of pricing and terms of use, and then, select **Deploy**.

## Consume NVIDIA NIM deployments

After your deployment is successfully created, you can go to **Models + Endpoints** under My assets in your Azure AI Foundry project, select your deployment under "Model deployments" and navigate to the Test tab for sample inference to the endpoint. You can also go to the Chat Playground by selecting **Open in Playground** in Deployment Details tab, to be able to modify parameters for the inference requests.   

NVIDIA NIMs on Foundry expose an OpenAI compatible API, learn more about the payload supported [here](https://docs.nvidia.com/nim/large-language-models/latest/api-reference.html#). The 'model' parameter for NIMs on Foundry is set to a default value within the container, and is not required to pass through in the payload to your online endpoint. The **Consume** tab of the NIM deployment on Foundry includes code samples for inference with the target URL of your deployment. You can also consume NIM deployments using the Azure AI Model Inference SDK. 

## Security scanning for NIMs by NVIDIA

NVIDIA ensures the security and reliability of NVIDIA NIM container images through best-in-class vulnerability scanning, rigorous patch management, and transparent processes. Learn the details [here](https://docs.nvidia.com/ai-enterprise/planning-resource/security-for-azure-ai-foundry/latest/introduction.html). Microsoft works with NVIDIA to get the latest patches of the NIMs to deliver secure, stable, and reliable production-grade software within AI Foundry.
Users can refer to the last updated time for the NIM in the model overview page, and you can redeploy to get the latest version of NIM from NVIDIA on Foundry.

Redeploy to get the latest version of NIM from NVIDIA on Foundry. 

## Network Isolation support for NIMs

While NIMs are in preview on Foundry, workspaces with Public Network Access disabled will have a limitation of being able to create only one successful deployment in the private workspace or project. Note, there can only be a single active deployment in a private workspace, attempts to create more active deployments will end in failure.

## Related content

* Learn more about the [Model Catalog](./model-catalog-overview.md)
* Learn more about [built-in policies for deployment](./built-in-policy-model-deployment.md)
