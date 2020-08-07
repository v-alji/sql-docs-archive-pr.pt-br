---
title: O que&#39;s New (Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, what's new
- what's new [Integration Services]
ms.assetid: da6999c7-e5e3-4a59-a284-1da635995af1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84f0b668407c89e1d6acc3c8cfbda73f129ca19a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582508"
---
# <a name="what39s-new-integration-services"></a><span data-ttu-id="4d9fa-102">O que&#39;s New (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="4d9fa-102">What&#39;s New (Integration Services)</span></span>
  [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="4d9fa-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]o não é alterado da versão anterior.</span><span class="sxs-lookup"><span data-stu-id="4d9fa-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is unchanged from the previous release.</span></span>  
  
 <span data-ttu-id="4d9fa-104">Para obter informações sobre outros [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] produtos e tecnologias, consulte [What ' s New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="4d9fa-104">For information about other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="4d9fa-105">Para obter mais informações sobre as alterações relacionadas à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence, consulte [What ' s New in Analysis Services and Business Intelligence](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="4d9fa-105">For more information about changes related to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence, see [What's New in Analysis Services and Business Intelligence](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span></span>  
  
##  <a name="rich-xml-validation-output-in-the-xml-task"></a><a name="ValidateXML"></a><span data-ttu-id="4d9fa-106">Saída de validação de XML rica na tarefa XML</span><span class="sxs-lookup"><span data-stu-id="4d9fa-106">Rich XML validation output in the XML Task</span></span>  
 <span data-ttu-id="4d9fa-107">Valide documentos XML e obtenha saída de erros completa habilitando a propriedade `ValidationDetails` da tarefa XML.</span><span class="sxs-lookup"><span data-stu-id="4d9fa-107">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span> <span data-ttu-id="4d9fa-108">Antes da disponibilidade da propriedade `ValidationDetails`, a validação do XML pela tarefa XML retornava apenas um resultado true ou false, sem informações sobre erros ou suas localizações.</span><span class="sxs-lookup"><span data-stu-id="4d9fa-108">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="4d9fa-109">Agora, quando você define `ValidationDetails` como true, o arquivo de saída contém informações detalhadas sobre cada erro, incluindo o número de linha e a posição.</span><span class="sxs-lookup"><span data-stu-id="4d9fa-109">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="4d9fa-110">Você pode usar essas informações para entender, localizar e corrigir erros em documentos XML.</span><span class="sxs-lookup"><span data-stu-id="4d9fa-110">You can use this information to understand, locate, and fix errors in XML documents.</span></span> <span data-ttu-id="4d9fa-111">Para obter mais informações, consulte [Validate XML with the XML Task](control-flow/xml-task.md).</span><span class="sxs-lookup"><span data-stu-id="4d9fa-111">For more info, see [Validate XML with the XML Task](control-flow/xml-task.md).</span></span>  
  
 <span data-ttu-id="4d9fa-112">O [!INCLUDE[ssIS](../includes/ssis-md.md)] introduziu a propriedade `ValidationDetails` no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="4d9fa-112">[!INCLUDE[ssIS](../includes/ssis-md.md)] introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="4d9fa-113">Essa nova propriedade não foi anunciada ou documentada naquele momento.</span><span class="sxs-lookup"><span data-stu-id="4d9fa-113">This new property was not announced or documented at that time.</span></span> <span data-ttu-id="4d9fa-114">A propriedade `ValidationDetails` também está disponível no [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] e no SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="4d9fa-114">The `ValidationDetails` property is also available in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9fa-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4d9fa-115">See Also</span></span>  
 [<span data-ttu-id="4d9fa-116">Recursos com suporte nas edições do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4d9fa-116">Features Supported by the Editions of SQL Server 2014</span></span>](../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
