---
title: Usando o provedor SQLXMLOLEDB (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXMLOLEDB Provider, samples
- ClientSideXML property
ms.assetid: fbcefac5-29c9-478b-b0e0-d510b593f446
author: rothja
ms.author: jroth
ms.openlocfilehash: 74e3c53eecd657d610c2fe90e108e0290e9b05b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574607"
---
# <a name="using-the-sqlxmloledb-provider-sqlxml-40"></a><span data-ttu-id="fe4c9-102">Usando o provedor SQLXMLOLEDB (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="fe4c9-102">Using the SQLXMLOLEDB Provider (SQLXML 4.0)</span></span>
  <span data-ttu-id="fe4c9-103">Os tópicos desta seção fornecem aplicativos de exemplo de ADO que ilustram o uso de propriedades específicas do provedor SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="fe4c9-103">The topics in this section provide ADO sample applications that illustrate the use of SQLXMLOLEDB Provider-specific properties.</span></span>  
  
## <a name="application-requirements-for-sqlxmloledb-40-provider"></a><span data-ttu-id="fe4c9-104">Requisitos de aplicativo para provedor SQLXMLOLEDB 4.0</span><span class="sxs-lookup"><span data-stu-id="fe4c9-104">Application Requirements for SQLXMLOLEDB 4.0 Provider</span></span>  
 <span data-ttu-id="fe4c9-105">Para criar exemplos de trabalho que usem SQLXMLOLEDB 4.0, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fe4c9-105">To create working samples that use SQLXMLOLEDB 4.0, you must do the following:</span></span>  
  
1.  <span data-ttu-id="fe4c9-106">Crie um aplicativo Microsoft Visual Basic .exe e adicione uma destas referências:</span><span class="sxs-lookup"><span data-stu-id="fe4c9-106">Create a Microsoft Visual Basic .exe application and add one of the following references:</span></span>  
  
    -   <span data-ttu-id="fe4c9-107">Biblioteca do Microsoft ActiveX Data Objects 2,6</span><span class="sxs-lookup"><span data-stu-id="fe4c9-107">Microsoft ActiveX Data Objects 2.6 Library</span></span>  
  
    -   <span data-ttu-id="fe4c9-108">Biblioteca do Microsoft ActiveX Data Objects 2,7</span><span class="sxs-lookup"><span data-stu-id="fe4c9-108">Microsoft ActiveX Data Objects 2.7 Library</span></span>  
  
    -   <span data-ttu-id="fe4c9-109">Biblioteca do Microsoft ActiveX Data Objects 2.8</span><span class="sxs-lookup"><span data-stu-id="fe4c9-109">Microsoft ActiveX Data Objects 2.8 Library</span></span>  
  
2.  <span data-ttu-id="fe4c9-110">Implante e instale o SQLXML 4.0 e o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="fe4c9-110">Deploy and install SQLXML 4.0 and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
     <span data-ttu-id="fe4c9-111">Para obter mais informações, consulte [conceitos de programação do SQLXML 4,0](../../sqlxml/sqlxml-4-0-programming-concepts.md) e [instalando SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="fe4c9-111">For more information, see on [SQLXML 4.0 Programming Concepts](../../sqlxml/sqlxml-4-0-programming-concepts.md) and [Installing SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe4c9-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="fe4c9-112">In This Section</span></span>  
 [<span data-ttu-id="fe4c9-113">Executando consultas SQL &#40;provedor de SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="fe4c9-113">Executing SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="fe4c9-114">Ilustra o uso das propriedades raiz ClientSideXML e XML para executar consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="fe4c9-114">Illustrates the use of the ClientSideXML and xml root properties to execute SQL queries.</span></span>  
  
 [<span data-ttu-id="fe4c9-115">Executando modelos que contêm consultas SQL &#40;provedor SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="fe4c9-115">Executing Templates That Contain SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="fe4c9-116">Ilustra o uso da propriedade ClientSideXML.</span><span class="sxs-lookup"><span data-stu-id="fe4c9-116">Illustrates the use of the ClientSideXML property.</span></span>  
  
 [<span data-ttu-id="fe4c9-117">Executando consultas XPath &#40;provedor SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="fe4c9-117">Executing XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="fe4c9-118">Ilustra o uso das propriedades de esquema ClientSideXML, caminho base e mapeamento.</span><span class="sxs-lookup"><span data-stu-id="fe4c9-118">Illustrates the use of the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="fe4c9-119">Executando consultas XPath com namespaces &#40;provedor SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="fe4c9-119">Executing XPath Queries with Namespaces &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-with-namespaces-sqlxmloledb-provider.md)  
 <span data-ttu-id="fe4c9-120">Ilustra como consultar esquemas qualificados para namespaces.</span><span class="sxs-lookup"><span data-stu-id="fe4c9-120">Illustrates how to query against namespace-qualified schemas.</span></span>  
  
 [<span data-ttu-id="fe4c9-121">Executando modelos que contêm consultas XPath &#40;provedor SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="fe4c9-121">Executing Templates That Contain XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="fe4c9-122">Ilustra como executar modelos com consultas SQL usando as propriedades de esquema ClientSideXML, caminho base e mapeamento.</span><span class="sxs-lookup"><span data-stu-id="fe4c9-122">Illustrates how to execute templates with SQL queries using the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="fe4c9-123">Aplicando um provedor XSL Transformation &#40;SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="fe4c9-123">Applying an XSL Transformation &#40;SQLXMLOLEDB Provider&#41;</span></span>](applying-an-xsl-transformation-sqlxmloledb-provider.md)  
 <span data-ttu-id="fe4c9-124">Ilustra o uso das propriedades ClientSideXML e XSL na aplicação de uma transformação XSL.</span><span class="sxs-lookup"><span data-stu-id="fe4c9-124">Illustrates the use of the ClientSideXML and xsl properties in applying an XSL transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4c9-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe4c9-125">See Also</span></span>  
 [<span data-ttu-id="fe4c9-126">Requisitos do sistema do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="fe4c9-126">System Requirements for SQL Server Native Client</span></span>](../../native-client/system-requirements-for-sql-server-native-client.md)  
  
  
