---
title: Opção de configuração de servidor SMO and DMO XPs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: bcd945ba-5d81-4124-9a2b-d87491c2a369
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f18fc6fafcf033113c983f990700158a10aec92a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684890"
---
# <a name="smo-and-dmo-xps-server-configuration-option"></a><span data-ttu-id="db475-102">Opção de configuração de servidor XPs SMO e DMO</span><span class="sxs-lookup"><span data-stu-id="db475-102">SMO and DMO XPs Server Configuration Option</span></span>
  <span data-ttu-id="db475-103">Use a opção SMO e DMO XPs para habilitar os procedimentos armazenados estendidos do SMO ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object) neste servidor.</span><span class="sxs-lookup"><span data-stu-id="db475-103">Use the SMO and DMO XPs option to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object (SMO) extended stored procedures on this server.</span></span>  
  
 <span data-ttu-id="db475-104">Observe que começando pelo [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], o DMO foi removido do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db475-104">Note than beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], DMO has been removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="db475-105">Os possíveis valores são descritos na tabela seguinte:</span><span class="sxs-lookup"><span data-stu-id="db475-105">The possible values are described in the following table:</span></span>  
  
|<span data-ttu-id="db475-106">Valor</span><span class="sxs-lookup"><span data-stu-id="db475-106">Value</span></span>|<span data-ttu-id="db475-107">Significado</span><span class="sxs-lookup"><span data-stu-id="db475-107">Meaning</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="db475-108">0</span><span class="sxs-lookup"><span data-stu-id="db475-108">0</span></span>|<span data-ttu-id="db475-109">Os SMO XPs não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="db475-109">SMO XPs are not available.</span></span>|  
|<span data-ttu-id="db475-110">1</span><span class="sxs-lookup"><span data-stu-id="db475-110">1</span></span>|<span data-ttu-id="db475-111">Os SMO XPs estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="db475-111">SMO XPs are available.</span></span> <span data-ttu-id="db475-112">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="db475-112">This is the default.</span></span>|  
  
 <span data-ttu-id="db475-113">A configuração entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="db475-113">The setting takes effect immediately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="db475-114">Exemplos</span><span class="sxs-lookup"><span data-stu-id="db475-114">Examples</span></span>  
 <span data-ttu-id="db475-115">O exemplo a seguir habilita os procedimentos armazenados estendidos do SMO.</span><span class="sxs-lookup"><span data-stu-id="db475-115">The following example enables SMO extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'SMO and DMO XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="db475-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db475-116">See Also</span></span>  
 [<span data-ttu-id="db475-117">Guia de Programação do SMO &#40;SQL Server Management Objects&#41;</span><span class="sxs-lookup"><span data-stu-id="db475-117">SQL Server Management Objects &#40;SMO&#41; Programming Guide</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
  
