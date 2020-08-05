---
title: Trabalhando com facetas do gerenciamento baseado em políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- viewing Policy-Based Management facets
- facets [Policy-Based Management], copying
- facets [Policy-Based Management], viewing
- copying Policy-Based Management facets
ms.assetid: 88d025c4-07c2-4e4d-8634-204249a8c82c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5a356550796cc682b2292defffd6565b7fea0783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571978"
---
# <a name="working-with-policy-based-management-facets"></a><span data-ttu-id="d36b0-102">Trabalhando com facetas do Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="d36b0-102">Working with Policy-Based Management Facets</span></span>
  <span data-ttu-id="d36b0-103">Uma faceta do Gerenciamento Baseado em Política é um conjunto de propriedades lógicas que estão relacionadas a uma área de interesse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="d36b0-103">A Policy-Based Management facet is a set of logical properties that are related to an area of management interest.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d36b0-104">inclui várias facetas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="d36b0-104">includes several predefined facets.</span></span> <span data-ttu-id="d36b0-105">Por exemplo, a faceta de Configuração da Área da Superfície define, como propriedades, os recursos que são desativados por padrão.</span><span class="sxs-lookup"><span data-stu-id="d36b0-105">For example, the Surface Area Configuration facet defines, as properties, the features that are off by default.</span></span>  
  
 <span data-ttu-id="d36b0-106">Quando você gerencia muitas instâncias de ambientes semelhantes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , é possível configurar uma faceta em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], copiar o estado da faceta em um arquivo e, em seguida, importar esse arquivo para outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como uma política.</span><span class="sxs-lookup"><span data-stu-id="d36b0-106">When you manage many similar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environments, you can configure a facet in one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], copy the state of the facet to a file, and then import that file into another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a policy.</span></span> <span data-ttu-id="d36b0-107">Quando o estado é convertido em uma política, a política pode ser aplicada outras instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], objetos de instância, bancos de dados ou objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d36b0-107">When the state has been converted to a policy, the policy can be applied to other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance objects, databases, or database objects.</span></span>  
  
 <span data-ttu-id="d36b0-108">Este tópico descreve como copiar o estado de uma faceta a um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="d36b0-108">This topic describes how to copy the state of a facet to an XML file.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d36b0-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="d36b0-109">Permissions</span></span>  
 <span data-ttu-id="d36b0-110">Os procedimentos deste tópico exigem a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="d36b0-110">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
## <a name="viewing-and-copying-facet-states"></a><span data-ttu-id="d36b0-111">Exibindo e copiando estados da faceta</span><span class="sxs-lookup"><span data-stu-id="d36b0-111">Viewing and Copying Facet States</span></span>  
 [<span data-ttu-id="d36b0-112">Exibir as facetas do gerenciamento baseado em políticas em um objeto do SQL Server</span><span class="sxs-lookup"><span data-stu-id="d36b0-112">View the Policy-Based Management Facets on a SQL Server Object</span></span>](view-the-policy-based-management-facets-on-a-sql-server-object.md)  
  
 [<span data-ttu-id="d36b0-113">Copiar um estado de faceta do gerenciamento baseado em políticas para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="d36b0-113">Copy a Policy-Based Management Facet State to an XML File</span></span>](copy-a-policy-based-management-facet-state-to-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="d36b0-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d36b0-114">See Also</span></span>  
 [<span data-ttu-id="d36b0-115">Administrar servidores com Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="d36b0-115">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
