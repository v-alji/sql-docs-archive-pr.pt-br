---
title: Usando DiffGrams para modificar dados no SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- data deletions [SQLXML]
- updating data [SQLXML]
- DiffGrams [SQLXML]
- modifying data [SQLXML]
- .NET Framework [SQLXML], DiffGrams
- XML [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- data modifications [SQLXML]
- record insertion [SQLXML]
- SQLXML, DiffGrams
- deleting data
- record updates [SQLXML]
- record deletions [SQLXML]
ms.assetid: 48b8a8f9-f3af-404f-8c84-f4c3703364d9
author: rothja
ms.author: jroth
ms.openlocfilehash: cc2e24304679a7648f18148eb45f33b9bf719a9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574591"
---
# <a name="using-diffgrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="2137e-102">Usando DiffGrams para modificar dados no SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="2137e-102">Using DiffGrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="2137e-103">O formato DiffGram é introduzido no componente **DataSet** do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2137e-103">The DiffGram format is introduced in the **DataSet** component of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="2137e-104">No .NET Framework, você pode criar DiffGrams e usá-los para modificar dados em tabelas de um banco de dados Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2137e-104">Within the .NET Framework, you can create DiffGrams and use them to modify data in tables in a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2137e-105">Esta seção fornece uma rápida introdução a DiffGrams e exemplos de como usá-los.</span><span class="sxs-lookup"><span data-stu-id="2137e-105">This section provides a brief introduction to DiffGrams and examples of how to use them.</span></span> <span data-ttu-id="2137e-106">Pressupõe-se que você esteja familiarizado com DiffGrams no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2137e-106">It is assumed that you are familiar with DiffGrams in the .NET Framework.</span></span> <span data-ttu-id="2137e-107">Nesta documentação, o foco principal está nos problemas de DiffGram específicos de SQLXML.</span><span class="sxs-lookup"><span data-stu-id="2137e-107">In this documentation, the primary focus is on DiffGram issues that are specific to SQLXML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2137e-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2137e-108">In This Section</span></span>  
 [<span data-ttu-id="2137e-109">Introdução a DiffGrams em SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="2137e-109">Introduction to DiffGrams in SQLXML 4.0</span></span>](introduction-to-diffgrams-in-sqlxml-4-0.md)  
 <span data-ttu-id="2137e-110">Fornece informações básicas sobre Diffgrams.</span><span class="sxs-lookup"><span data-stu-id="2137e-110">Provides basic information about Diffgrams.</span></span>  
  
 [<span data-ttu-id="2137e-111">Exemplos de DiffGram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="2137e-111">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
 <span data-ttu-id="2137e-112">Fornece exemplos de como usar Diffgrams.</span><span class="sxs-lookup"><span data-stu-id="2137e-112">Provides examples of using Diffgrams.</span></span>  
  
 [<span data-ttu-id="2137e-113">Executando um DiffGram usando o ADO &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="2137e-113">Executing a DiffGram by Using ADO &#40;SQLXML 4.0&#41;</span></span>](executing-a-diffgram-by-using-ado-sqlxml-4-0.md)  
 <span data-ttu-id="2137e-114">Fornece um exemplo de como executar um Diffgram com ADO (ActiveX Data Objects).</span><span class="sxs-lookup"><span data-stu-id="2137e-114">Provides an example of executing a Diffgram with ActiveX Data Objects (ADO).</span></span>  
  
 [<span data-ttu-id="2137e-115">Executando um DiffGram usando as classes gerenciadas SQLXML</span><span class="sxs-lookup"><span data-stu-id="2137e-115">Executing a DiffGram by Using SQLXML Managed Classes</span></span>](../net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="2137e-116">Fornece um exemplo de como executar um Diffgram com Classes Gerenciadas do SQLXML.</span><span class="sxs-lookup"><span data-stu-id="2137e-116">Provides an example of executing a Diffgram with SQLXML Managed Classes.</span></span>  
  
  
