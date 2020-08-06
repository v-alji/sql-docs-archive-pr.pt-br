---
title: Transformação de Limpeza DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data correction
- correct data
ms.assetid: d2ec1b1a-c745-4741-b57c-6fdb524a154c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e980497905b8fa96a73516916af17f934221992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569569"
---
# <a name="dqs-cleansing-transformation"></a><span data-ttu-id="fbad6-102">Transformação de Limpeza DQS</span><span class="sxs-lookup"><span data-stu-id="fbad6-102">DQS Cleansing Transformation</span></span>
  <span data-ttu-id="fbad6-103">A transformação de Limpeza DQS usa o DQS (Data Quality Services) para corrigir dados de uma fonte de dados conectada com a aplicação de regras aprovadas, que foram criadas para a fonte de dados conectada ou uma fonte de dados semelhante.</span><span class="sxs-lookup"><span data-stu-id="fbad6-103">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data from a connected data source, by applying approved rules that were created for the connected data source or a similar data source.</span></span> <span data-ttu-id="fbad6-104">Para obter informações sobre regras de correção de dados, consulte [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="fbad6-104">For more information about data correction rules, see [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span> <span data-ttu-id="fbad6-105">Para obter mais informações sobre o DQS, consulte [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="fbad6-105">For more information DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="fbad6-106">Para determinar se os dados precisam ser corrigidos, a transformação de Limpeza DQS processa dados de uma coluna de entrada quando as seguintes condições são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="fbad6-106">To determine whether the data has to be corrected, the DQS Cleansing transformation processes data from an input column when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="fbad6-107">A coluna é selecionada para correção de dados.</span><span class="sxs-lookup"><span data-stu-id="fbad6-107">The column is selected for data correction.</span></span>  
  
-   <span data-ttu-id="fbad6-108">O tipo de dados da coluna tem suporte da correção de dados.</span><span class="sxs-lookup"><span data-stu-id="fbad6-108">The column data type is supported for data correction.</span></span>  
  
-   <span data-ttu-id="fbad6-109">A coluna é mapeada para um domínio que tem um tipo de dados compatível.</span><span class="sxs-lookup"><span data-stu-id="fbad6-109">The column is mapped a domain that has a compatible data type.</span></span>  
  
 <span data-ttu-id="fbad6-110">A transformação também inclui uma saída de erro que você configura para tratar erros em nível de linha.</span><span class="sxs-lookup"><span data-stu-id="fbad6-110">The transformation also includes an error output that you configure to handle row-level errors.</span></span> <span data-ttu-id="fbad6-111">Para configurar a saída de erro, use o **Editor de Transformação de Limpeza DQS**.</span><span class="sxs-lookup"><span data-stu-id="fbad6-111">To configure the error output, use the **DQS Cleansing Transformation Editor**.</span></span>  
  
 <span data-ttu-id="fbad6-112">Você pode incluir [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) no fluxo de dados para identificar linhas de dados que são provavelmente duplicadas.</span><span class="sxs-lookup"><span data-stu-id="fbad6-112">You can include the [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) in the data flow to identify rows of data that are likely to be duplicates.</span></span>  
  
## <a name="data-quality-projects-and-values"></a><span data-ttu-id="fbad6-113">Projetos de qualidade de dados e valores</span><span class="sxs-lookup"><span data-stu-id="fbad6-113">Data Quality Projects and Values</span></span>  
 <span data-ttu-id="fbad6-114">Quando você processar dados com a transformação de limpeza DQS, um projeto de limpeza é criado no Data Quality Server.</span><span class="sxs-lookup"><span data-stu-id="fbad6-114">When you process data with the DQS Cleansing transformation, a cleansing project is created on the Data Quality Server.</span></span> <span data-ttu-id="fbad6-115">Você usa o Cliente Data Quality para gerenciar o projeto.</span><span class="sxs-lookup"><span data-stu-id="fbad6-115">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="fbad6-116">Além disso, você pode usar o Cliente Data Quality para importar os valores de projeto em um domínio da base de dados de conhecimento do DQS.</span><span class="sxs-lookup"><span data-stu-id="fbad6-116">In addition, you can use the Data Quality Client to import the project values into a DQS knowledge base domain.</span></span> <span data-ttu-id="fbad6-117">Você só pode importar os valores para um domínio (ou domínio vinculado) que a transformação de limpeza DQS tiver configurado para usar.</span><span class="sxs-lookup"><span data-stu-id="fbad6-117">You can import the values only to a domain (or linked domain) that the DQS Cleansing transformation was configured to use.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="fbad6-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="fbad6-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fbad6-119">Abrir projetos do Integration Services no Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="fbad6-119">Open Integration Services Projects in Data Quality Client</span></span>](../../../data-quality-services/open-integration-services-projects-in-data-quality-client.md)  
  
-   [<span data-ttu-id="fbad6-120">Importar valores de projeto de limpeza para um domínio</span><span class="sxs-lookup"><span data-stu-id="fbad6-120">Import Cleansing Project Values into a Domain</span></span>](../../../data-quality-services/import-cleansing-project-values-into-a-domain.md)  
  
-   [<span data-ttu-id="fbad6-121">Aplicar regras de qualidade de dados à fonte de dados</span><span class="sxs-lookup"><span data-stu-id="fbad6-121">Apply Data Quality Rules to Data Source</span></span>](apply-data-quality-rules-to-data-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="fbad6-122">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="fbad6-122">Related Content</span></span>  
  
-   [<span data-ttu-id="fbad6-123">Gerenciar &#40;abrir, desbloquear, renomear e excluir&#41; um projeto de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="fbad6-123">Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project</span></span>](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md)  
  
-   <span data-ttu-id="fbad6-124">Artigo [Dados complexos de limpeza usando domínios compostos](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx)em social.technet.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fbad6-124">Article, [Cleansing complex data using composite domains](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx), on social.technet.microsoft.com.</span></span>  
  
  
