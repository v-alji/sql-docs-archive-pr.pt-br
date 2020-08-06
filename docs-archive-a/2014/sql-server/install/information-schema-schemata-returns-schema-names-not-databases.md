---
title: INFORMATION_SCHEMA. SCHEMATA retorna os nomes de esquema em um banco de dados, não em uma instância | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- INFORMATION_SCHEMA.SCHEMATA view
ms.assetid: 4337b643-910d-47d7-bea8-f4052066b9a2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cb2a34a59bf6257c188210fc7bf2aeacb70f6b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582775"
---
# <a name="information_schemaschemata-returns-schema-names-in-a-database-not-databases-in-an-instance"></a><span data-ttu-id="cff4a-102">INFORMATION_SCHEMA.SCHEMATA retorna nomes de esquemas em um banco de dados, e não bancos de dados em uma instância</span><span class="sxs-lookup"><span data-stu-id="cff4a-102">INFORMATION_SCHEMA.SCHEMATA returns schema names in a database, not databases in an instance</span></span>
  <span data-ttu-id="cff4a-103">O Supervisor de Atualização detectou instruções que referenciam a exibição INFORMATION_SCHEMA.SCHEMATA.</span><span class="sxs-lookup"><span data-stu-id="cff4a-103">Upgrade Advisor detected statements that reference the INFORMATION_SCHEMA.SCHEMATA view.</span></span> <span data-ttu-id="cff4a-104">Em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], essa exibição retornava todos os bancos de dados em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cff4a-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cff4a-105">No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e em versões posteriores, a exibição retorna todos os esquemas em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cff4a-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later, the view returns all schemas in a database.</span></span>  
  
## <a name="component"></a><span data-ttu-id="cff4a-106">Componente</span><span class="sxs-lookup"><span data-stu-id="cff4a-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="cff4a-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="cff4a-107">Description</span></span>  
 <span data-ttu-id="cff4a-108">Em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a exibição INFORMATION_SCHEMA.SCHEMATA retornava todos os bancos de dados em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cff4a-108">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the INFORMATION_SCHEMA.SCHEMATA view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cff4a-109">Agora, a exibição retorna todos os esquemas em um banco de dados, o que obedece ao padrão do SQL.</span><span class="sxs-lookup"><span data-stu-id="cff4a-109">Now, the view returns all schemas in a database, which complies with the SQL Standard.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="cff4a-110">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="cff4a-110">Corrective Action</span></span>  
 <span data-ttu-id="cff4a-111">Modifique seu aplicativo para fazer referência à exibição de catálogo **Sys. databases** para retornar todos os bancos de dados em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cff4a-111">Modify your application to reference the **sys.databases** catalog view to return all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff4a-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cff4a-112">See Also</span></span>  
 <span data-ttu-id="cff4a-113">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="cff4a-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="cff4a-114">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="cff4a-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
