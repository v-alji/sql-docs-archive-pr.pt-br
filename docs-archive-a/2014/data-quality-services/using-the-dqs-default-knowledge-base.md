---
title: Usando a base de dados de conhecimento padrão do DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b36af13b-9fcc-4168-bb92-214d600b1c93
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3261c7af28bb5710ede203d1fe27c6540286e9f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570849"
---
# <a name="using-the-dqs-default-knowledge-base"></a><span data-ttu-id="ef1d6-102">Usando a base de dados de conhecimento padrão do DQS</span><span class="sxs-lookup"><span data-stu-id="ef1d6-102">Using the DQS Default Knowledge Base</span></span>
  <span data-ttu-id="ef1d6-103">Este tópico descreve a base de dados de conhecimento padrão, os **Dados do DQS**que são instalados com o [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="ef1d6-103">This topic describes the default knowledge base, **DQS Data**, which is installed with [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="ef1d6-104">Esta é uma base de conhecimento padrão pré-criada que contém os seguintes domínios:</span><span class="sxs-lookup"><span data-stu-id="ef1d6-104">This is a pre-built default knowledge base that contains the following domains:</span></span>  
  
-   <span data-ttu-id="ef1d6-105">**País/Região**: contêm os nomes convencionais longos (nome oficial conforme designado pelo país/região) e nomes curtos (nome comum usado em listas, mapas, etc.), abreviação de duas letras, abreviação de três letras e código de três dígitos para cada local.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-105">**Country/Region**: Contains the conventional long (official name as designated by the country/region ) and short names (common name used in lists, on maps, etc. ), two-letter abbreviation, three-letter abbreviation and three-digit code for each location.</span></span>  <span data-ttu-id="ef1d6-106">O valor principal é definido como o nome longo do país.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-106">Leading value is set to the long country name.</span></span>  
  
-   <span data-ttu-id="ef1d6-107">**País/Região (prefixo de três letras)**: contêm os nomes convencionais longos (nome oficial conforme designado pelo país/região) e nomes curtos (nome comum usado em listas, mapas etc), abreviação de duas letras, abreviação de três letras e código de três dígitos para cada local.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-107">**Country/Region (three-letter leading)**: Contains the conventional long (official name as designated by the country/region) and short names (common name used in lists, on maps, and so on), two-letter abbreviation, three-letter abbreviation and three-digit code for each location.</span></span>  <span data-ttu-id="ef1d6-108">Os valores principais são definidos como uma abreviação de três letras do Município.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-108">Leading values is set to County three-letter abbreviation.</span></span>  
  
-   <span data-ttu-id="ef1d6-109">**País/Região (prefixo de duas letras)**: contêm os nomes convencionais longos (nome oficial conforme designado pelo país/região) e nomes curtos (nome comum usado em listas, mapas, etc.), abreviação de duas letras, abreviação de três letras e código de três dígitos para cada local.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-109">**Country/Region (two-letter leading)**: Contains the conventional long (official name as designated by the country/region ) and short names (common name used in lists, on maps, etc. ), two-letter abbreviation, three-letter abbreviation and three-digit code for each location.</span></span>  <span data-ttu-id="ef1d6-110">O valor principal é definido como uma abreviação de duas letras do País.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-110">Leading value is set to the Country two-letter abbreviation.</span></span>  
  
-   <span data-ttu-id="ef1d6-111">**EUA - Municípios**: contém uma lista de municípios de EUA.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-111">**US - Counties**: Contains a list of US counties.</span></span>  
  
-   <span data-ttu-id="ef1d6-112">**EUA - Sobrenome**: contém uma lista de sobrenomes que ocorrem 100 ou mais vezes no Censo 2000.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-112">**US - Last Name**: Contains a list of last names (surnames) occurring 100 or more times in the Census 2000.</span></span>  
  
-   <span data-ttu-id="ef1d6-113">**EUA - Locais**: contém uma lista de locais para os 50 estados, o Distrito de Columbia e Porto Rico extraídos do Censo 2010.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-113">**US - Places**: Contains a list of places for the 50 states, the District of Columbia, and Puerto Rico extracted from the Census 2010.</span></span>  
  
-   <span data-ttu-id="ef1d6-114">**EUA - Estado**: contém o nome convencional longo (oficial) e a abreviação de duas letras para cada estado nos EUA.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-114">**US - State**: Contains the conventional long (official) name and two-letter abbreviation for each state in US.</span></span> <span data-ttu-id="ef1d6-115">O valor principal é definido como o nome convencional do estado.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-115">Leading value is set to the conventional state name.</span></span>  
  
-   <span data-ttu-id="ef1d6-116">**EUA – Estado (título com 2 letras)**: contém o nome convencional longo (oficial) e a abreviação de duas letras para cada estado nos EUA.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-116">**US - State (2-letter heading)**: Contains the conventional long (official) name and two-letter abbreviation for each state in US.</span></span> <span data-ttu-id="ef1d6-117">O valor principal é definido como um nome de estado com abreviação de duas letras.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-117">Leading value is set to the two-letter abbreviation state name.</span></span>  
  
## <a name="using-the-default-knowledge-base"></a><span data-ttu-id="ef1d6-118">Usando a base de dados de conhecimento padrão</span><span class="sxs-lookup"><span data-stu-id="ef1d6-118">Using the Default Knowledge Base</span></span>  
 <span data-ttu-id="ef1d6-119">Você pode usar a base de dados de conhecimento padrão do DQS, os Dados do DQS, das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="ef1d6-119">You can use the default DQS knowledge base, DQS Data, in the following ways:</span></span>  
  
-   <span data-ttu-id="ef1d6-120">Inicie e execute rapidamente um projeto de qualidade de dados de limpeza usando a base de dados de conhecimento padrão sem ter que primeiro criar uma nova base de dados de conhecimento em DQS.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-120">Quickly start and run a cleansing data quality project using the default knowledge base without first having to create a new knowledge base in DQS.</span></span>  
  
-   <span data-ttu-id="ef1d6-121">Execute o Gerenciamento de Domínio, a Descoberta de Conhecimento ou as atividades de Política de Correspondência na base de dados de conhecimento padrão.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-121">Run the Domain Management, Knowledge Discovery, or Matching Policy activities on the default knowledge base.</span></span> <span data-ttu-id="ef1d6-122">Para fazer isso, clique em **Abrir Base de Dados de Conhecimento** na [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md), selecione a base de dados de conhecimento **Dados do DQS** na tela **Abrir Base de Dados de Conhecimento** e, em seguida, selecione a atividade na área **Selecionar Atividade** .</span><span class="sxs-lookup"><span data-stu-id="ef1d6-122">To do so, click **Open Knowledge Base** in the [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md), select the **DQS Data** knowledge base in the **Open Knowledge Base** screen, and then select the required activity in the **Select Activity** area.</span></span> <span data-ttu-id="ef1d6-123">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-123">Click **Next** to proceed.</span></span>  
  
-   <span data-ttu-id="ef1d6-124">Crie uma nova base de dados de conhecimento usando a base de dados de conhecimento padrão.</span><span class="sxs-lookup"><span data-stu-id="ef1d6-124">Create a new knowledge base using the default knowledge base.</span></span> <span data-ttu-id="ef1d6-125">Para criar uma base de dados de conhecimento de uma base de conhecimento existente, consulte [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="ef1d6-125">To create a knowledge base from an existing knowledge base, see [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md).</span></span>  
  
-   <span data-ttu-id="ef1d6-126">Use-a no [Componente de limpeza DQS no Integration Services](https://go.microsoft.com/fwlink/?LinkId=238830) e [Suplemento do Master Data Services para Excel](../master-data-services/microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="ef1d6-126">Use it in the [DQS Cleansing component in Integration Services](https://go.microsoft.com/fwlink/?LinkId=238830) and [Master Data Services Add-in for Excel](../master-data-services/microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef1d6-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ef1d6-127">See Also</span></span>  
 [<span data-ttu-id="ef1d6-128">Bases de Dados de Conhecimento DQS e domínios</span><span class="sxs-lookup"><span data-stu-id="ef1d6-128">DQS Knowledge Bases and Domains</span></span>](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md)  
  
  
