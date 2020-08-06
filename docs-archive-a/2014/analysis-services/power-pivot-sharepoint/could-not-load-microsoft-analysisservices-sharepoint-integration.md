---
title: Não foi possível carregar o arquivo ou assembly &#39;Microsoft. Data. Services, versão = 3.5.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089&#39; ou uma de suas dependências. O sistema não pode encontrar o arquivo especificado. | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 81ed0f44-8782-462d-af8f-0ba5b975df27
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f9eed7ad90c1e720d07c714e351c24ae6657717
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581531"
---
# <a name="could-not-load-file-or-assembly-39microsoftdataservices-version3500-cultureneutral-publickeytokenb77a5c561934e08939-or-one-of-its-dependencies-the-system-cannot-find-the-file-specified"></a><span data-ttu-id="0a9d9-104">Não foi possível carregar o arquivo ou assembly &#39;Microsoft. Data. Services, versão = 3.5.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089&#39; ou uma de suas dependências.</span><span class="sxs-lookup"><span data-stu-id="0a9d9-104">Could not load file or assembly &#39;Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089&#39; or one of its dependencies.</span></span> <span data-ttu-id="0a9d9-105">O sistema não pode encontrar o arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="0a9d9-105">The system cannot find the file specified.</span></span>
  <span data-ttu-id="0a9d9-106">Em ambientes do SharePoint 2010 com o PowerPivot para SharePoint, este erro ocorrerá se você tentar fazer uma exportação de feed de dados e o sistema não contiver a versão necessária do Microsoft ADO.NET Data Services.</span><span class="sxs-lookup"><span data-stu-id="0a9d9-106">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if you attempt a data feed export and the system is missing the required version of Microsoft ADO.NET Data Services.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0a9d9-107">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0a9d9-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a9d9-108">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="0a9d9-108">Applies to</span></span>|<span data-ttu-id="0a9d9-109">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="0a9d9-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="0a9d9-110">Versão do produto</span><span class="sxs-lookup"><span data-stu-id="0a9d9-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="0a9d9-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a9d9-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="0a9d9-112">Causa</span><span class="sxs-lookup"><span data-stu-id="0a9d9-112">Cause</span></span>|<span data-ttu-id="0a9d9-113">O ADO.NET Data Services 3.5 SP1 não foi localizado.</span><span class="sxs-lookup"><span data-stu-id="0a9d9-113">ADO.NET Data Services 3.5 SP1 was not found.</span></span>|  
|<span data-ttu-id="0a9d9-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="0a9d9-114">Message Text</span></span>|<span data-ttu-id="0a9d9-115">Não foi possível carregar o arquivo ou assembly 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' ou uma de suas dependências.</span><span class="sxs-lookup"><span data-stu-id="0a9d9-115">Could not load file or assembly 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies.</span></span> <span data-ttu-id="0a9d9-116">O sistema não pôde localizar o arquivo especificado</span><span class="sxs-lookup"><span data-stu-id="0a9d9-116">The system cannot find the file specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0a9d9-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="0a9d9-117">Explanation</span></span>  
 <span data-ttu-id="0a9d9-118">O SharePoint 2010 inclui um botão Exportar como Feed de Dados que pode ser usado para exportar uma lista do SharePoint como um feed de dados XML.</span><span class="sxs-lookup"><span data-stu-id="0a9d9-118">SharePoint 2010 includes an Export as Data Feed button that you can use to export a SharePoint list as an XML data feed.</span></span> <span data-ttu-id="0a9d9-119">Além disso, o Reporting Services no modo do SharePoint e o PowerPivot para SharePoint oferecem suporte aos recursos de feed de dados que exigem o ADO.NET Data Services.</span><span class="sxs-lookup"><span data-stu-id="0a9d9-119">In addition, both Reporting Services in SharePoint mode and PowerPivot for SharePoint support data feed features that require ADO.NET Data Services.</span></span>  
  
 <span data-ttu-id="0a9d9-120">Se o ADO.NET Data Services não estiver instalado, esse erro ocorrerá quando você solicitar um feed de dados.</span><span class="sxs-lookup"><span data-stu-id="0a9d9-120">If ADO.NET Data Services is not installed, this error will occur when you request a data feed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a9d9-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="0a9d9-121">User Action</span></span>  
  
1.  <span data-ttu-id="0a9d9-122">Acesse a documentação de requisitos de hardware e software para o SharePoint 2010, para [determinar os requisitos de hardware e software (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) ( https://go.microsoft.com/fwlink/?LinkId=169734) .</span><span class="sxs-lookup"><span data-stu-id="0a9d9-122">Go to the hardware and software requirements documentation for SharePoint 2010, [Determine Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) (https://go.microsoft.com/fwlink/?LinkId=169734).</span></span>  
  
2.  <span data-ttu-id="0a9d9-123">Em **Instalando pré-requisitos de software**, localize o link para o ADO.NET Data Services 3.5 que corresponde ao sistema operacional você está usando.</span><span class="sxs-lookup"><span data-stu-id="0a9d9-123">In **Installing software prerequisites**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using.</span></span>  
  
3.  <span data-ttu-id="0a9d9-124">Clique no link e execute o programa de instalação que instala o serviço.</span><span class="sxs-lookup"><span data-stu-id="0a9d9-124">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9d9-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a9d9-125">See Also</span></span>  
 [<span data-ttu-id="0a9d9-126">Implantar soluções PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="0a9d9-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
