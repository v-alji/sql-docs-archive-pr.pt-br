---
title: Alterações recentes em recursos das ferramentas de gerenciamento no SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 11/27/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 3ff3fad8-b569-4516-bd58-5a3efeb537e2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0487b6ab0958e0b83d4e8e34be507b5b3211ac87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575383"
---
# <a name="breaking-changes-to-management-tools-features-in-sql-server-2014"></a><span data-ttu-id="60efe-102">Alterações de quebra feitas em recursos das Ferramentas de Gerenciamento do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="60efe-102">Breaking Changes to Management Tools Features in SQL Server 2014</span></span>
  <span data-ttu-id="60efe-103">Este tópico descreve alterações de quebra feitas em recursos das ferramentas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="60efe-103">This topic describes breaking changes to management tools features.</span></span> <span data-ttu-id="60efe-104">Essas alterações podem danificar aplicativos, scripts ou funcionalidades baseados em versões anteriores do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60efe-104">These changes might break applications, scripts, or functionalities that are based on earlier versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="60efe-105">Talvez você tenha esses problemas ao atualizar.</span><span class="sxs-lookup"><span data-stu-id="60efe-105">You might encounter these issues when you upgrade.</span></span> <span data-ttu-id="60efe-106">Para obter mais informações, consulte [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="60efe-106">For more information, see [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span></span>  
  
## <a name="breaking-changes-in-sssql14"></a><span data-ttu-id="60efe-107">Últimas alterações do [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60efe-107">Breaking Changes in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
 <span data-ttu-id="60efe-108">Informações que virão posteriormente.</span><span class="sxs-lookup"><span data-stu-id="60efe-108">Information to come later.</span></span>  
  
## <a name="breaking-changes-in-sssql11"></a><span data-ttu-id="60efe-109">Últimas alterações do [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60efe-109">Breaking Changes in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
  
### <a name="you-cannot-use-sssql11-management-tools-to-create-a-utility-control-point-on-a-sskilimanjaro-instance-of-sql-server"></a><span data-ttu-id="60efe-110">Você não pode usar as Ferramentas de Gerenciamento do [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] para criar um ponto de controle de utilitário em uma instância do [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] do SQL Server</span><span class="sxs-lookup"><span data-stu-id="60efe-110">You cannot use [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Management Tools to create a utility control point on a [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] instance of SQL Server</span></span>  
 <span data-ttu-id="60efe-111">Para criar um ponto de controle de utilitário em uma instância do [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)]use as Ferramentas de Gerenciamento do [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60efe-111">To create a utility control point on an instance of [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], use [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] Management Tools.</span></span>  
  
### <a name="smo-has-been-reversioned-in-sssql11"></a><span data-ttu-id="60efe-112">O SMO foi revertido no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60efe-112">SMO has been reversioned in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
 <span data-ttu-id="60efe-113">O código desenvolvido com o SMO do [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] ou de versões anteriores talvez não seja criado no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] sem pequenas modificações.</span><span class="sxs-lookup"><span data-stu-id="60efe-113">Code developed with SMO from [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] or earlier versions might not build against [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] without minor modifications.</span></span> <span data-ttu-id="60efe-114">Para obter mais informações, consulte [Backward Compatibility in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span><span class="sxs-lookup"><span data-stu-id="60efe-114">For more information, see [Backward Compatibility in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span></span>  

## <a name="breaking-changes-in-sql-server-2005"></a><a name="previous-versions"></a><span data-ttu-id="60efe-115">Alterações recentes no SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="60efe-115">Breaking Changes in SQL Server 2005</span></span>  

[!INCLUDE[Archived documentation for very old versions of SQL Server](../includes/paragraph-content/previous-versions-archive-documentation-sql-server.md)]

## <a name="see-also"></a><span data-ttu-id="60efe-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60efe-116">See Also</span></span>  
 [<span data-ttu-id="60efe-117">Compatibilidade com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="60efe-117">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
 [<span data-ttu-id="60efe-118">Mais informações sobre alterações recentes em recursos das ferramentas de gerenciamento no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="60efe-118">More about Breaking Changes to Management Tools Features in SQL Server 2014</span></span>](breaking-changes-to-database-engine-features-in-sql-server-2016.md?view=sql-server-2014)  
  
  
