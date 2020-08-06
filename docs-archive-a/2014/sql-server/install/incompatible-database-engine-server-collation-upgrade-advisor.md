---
title: Agrupamento de servidor Mecanismo de Banco de Dados incompatível (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f499d6-2c90-49eb-a5b3-0bb5b7faaa3b
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b6ce0555bdf5a878e56d87a8bd55b5ce6c4b2649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582776"
---
# <a name="incompatible-database-engine-server-collation-upgrade-advisor"></a><span data-ttu-id="0bf63-102">Ordenação do servidor de mecanismo de banco de dados incompatível (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="0bf63-102">Incompatible Database Engine Server Collation (Upgrade Advisor)</span></span>
  <span data-ttu-id="0bf63-103">O supervisor de atualização detectado [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] está usando uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que está configurada para usar um agrupamento de servidor incompatível.</span><span class="sxs-lookup"><span data-stu-id="0bf63-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
||  
|-|  
|<span data-ttu-id="0bf63-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0bf63-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="0bf63-105">Componente</span><span class="sxs-lookup"><span data-stu-id="0bf63-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="0bf63-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="0bf63-106">Description</span></span>  
 <span data-ttu-id="0bf63-107">O supervisor de atualização detectado [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] está usando uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que está configurada para usar um agrupamento de servidor incompatível.</span><span class="sxs-lookup"><span data-stu-id="0bf63-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="0bf63-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]O modo do SharePoint utiliza a arquitetura de serviços compartilhados do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0bf63-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode utilizes the SharePoint shared services architecture.</span></span> <span data-ttu-id="0bf63-109">O SharePoint não oferece suporte a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configurado para diferenciação de maiúsculas e minúsculas ou ordenações do servidor ou ordenações do servidor binários.</span><span class="sxs-lookup"><span data-stu-id="0bf63-109">SharePoint does not support [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configured for case sensitive or server collations or binary server collations.</span></span> <span data-ttu-id="0bf63-110">Ordenações incompatíveis incluem ordenações que têm por padrão a diferenciação de maiúsculas e minúsculas ou binários e uma ordenação básica que, por padrão, é compatível mas foi configurada com qualquer um dos seguintes designadores de ordenação:</span><span class="sxs-lookup"><span data-stu-id="0bf63-110">Incompatible collations include collations that are by default case sensitive or binary and a base collation that by default is compatible but has been configured with any of the following collation designators:</span></span>  
  
-   <span data-ttu-id="0bf63-111">**Binary**</span><span class="sxs-lookup"><span data-stu-id="0bf63-111">**Binary**</span></span>  
  
-   <span data-ttu-id="0bf63-112">**Diferenciar maiúsculas de minúsculas**</span><span class="sxs-lookup"><span data-stu-id="0bf63-112">**Case-sensitive**</span></span>  
  
-   <span data-ttu-id="0bf63-113">**Ponto de código binário**</span><span class="sxs-lookup"><span data-stu-id="0bf63-113">**Binary-codepoint**</span></span>  
  
 <span data-ttu-id="0bf63-114">Como a ordenação do servidor [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] atual é incompatível, a atualização está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="0bf63-114">Because the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation is incompatible, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="0bf63-115">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="0bf63-115">Corrective Action</span></span>  
 <span data-ttu-id="0bf63-116">A propriedade de ordenação do servidor [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="0bf63-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation property cannot be changed.</span></span> <span data-ttu-id="0bf63-117">Você não poderá concluir uma atualização do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bf63-117">You will not be able to complete an upgrade of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="0bf63-118">Você precisará migrar sua instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para um novo servidor que está usando uma ordenação do servidor compatível.</span><span class="sxs-lookup"><span data-stu-id="0bf63-118">You will need to migrate your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation to a new server which is using a compatible server collation.</span></span> <span data-ttu-id="0bf63-119">Para saber mais, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0bf63-119">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="0bf63-120">Atualizar e migrar o Reporting Services</span><span class="sxs-lookup"><span data-stu-id="0bf63-120">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=233227)  
  
-   [<span data-ttu-id="0bf63-121">Selecionando uma ordenação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="0bf63-121">Selecting a SQL Server Collation</span></span>](https://go.microsoft.com/fwlink/?LinkId=233226)  
  
  
