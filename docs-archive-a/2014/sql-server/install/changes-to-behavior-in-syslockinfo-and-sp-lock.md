---
title: Alterações no comportamento em syslockinfo e sp_lock | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- syslockinfo
- sp_lock
ms.assetid: b9892ae3-ac15-48be-8b52-78dbed6467ed
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65ace190004cab911dd8996642720620eba94935
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573524"
---
# <a name="changes-to-behavior-in-syslockinfo-and-sp_lock"></a><span data-ttu-id="29ec4-102">Alterações no comportamento em syslockinfo e sp_lock</span><span class="sxs-lookup"><span data-stu-id="29ec4-102">Changes to behavior in syslockinfo and sp_lock</span></span>
  <span data-ttu-id="29ec4-103">O**syslockinfo** e o **sp_lock** podem retornar valores inesperados.</span><span class="sxs-lookup"><span data-stu-id="29ec4-103">**syslockinfo** and **sp_lock** may return unexpected values.</span></span> <span data-ttu-id="29ec4-104">Eles também podem retornar linhas adicionais, enquanto que versões anteriores de **syslockinfo** e **sp_lock** retornavam, no máximo, duas linhas por recurso de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="29ec4-104">They may also return additional rows, whereas previous versions of **syslockinfo** and **sp_lock** returned a maximum of two rows per lock resource.</span></span>  
  
 <span data-ttu-id="29ec4-105">Para acessar informações de **syslockinfo** ou executar **sp_lock** , é necessário ter permissão VIEW SERVER STATE no servidor.</span><span class="sxs-lookup"><span data-stu-id="29ec4-105">To access information from **syslockinfo** or execute **sp_lock** requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="component"></a><span data-ttu-id="29ec4-106">Componente</span><span class="sxs-lookup"><span data-stu-id="29ec4-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="29ec4-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="29ec4-107">Description</span></span>  
 <span data-ttu-id="29ec4-108">No [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], as colunas **rsc_objid** e **rsc_indid** no **syslockinfo** , e as colunas **objid** e **indid** no **sp_lock** retornam, consistentemente, a identificação do objeto e a identificação do índice.</span><span class="sxs-lookup"><span data-stu-id="29ec4-108">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the **rsc_objid** and **rsc_indid** columns in **syslockinfo** and the **objid** and **indid** columns in **sp_lock** consistently return the object ID and index ID.</span></span> <span data-ttu-id="29ec4-109">No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], o valor 0 pode ser retornado.</span><span class="sxs-lookup"><span data-stu-id="29ec4-109">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a value of 0 may be returned.</span></span>  
  
 <span data-ttu-id="29ec4-110">No [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], **syslockinfo** e **sp_lock** retornam, no máximo, duas linhas para qualquer recurso de bloqueio em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="29ec4-110">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], **syslockinfo** and **sp_lock** return a maximum of two rows for any given lock resource in a single transaction.</span></span> <span data-ttu-id="29ec4-111">A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], quando o particionamento de bloqueio passou a ser habilitado, várias linhas podem ser retornadas para o mesmo recurso executado em uma transação.</span><span class="sxs-lookup"><span data-stu-id="29ec4-111">Starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], when lock partitioning is enabled, multiple rows for the same resource running under one transaction may be returned.</span></span> <span data-ttu-id="29ec4-112">Pode haver até N + 1 linhas retornadas, em que N é o número de CPUs.</span><span class="sxs-lookup"><span data-stu-id="29ec4-112">There may be up to N + 1 rows returned, where N is the number of CPUs.</span></span> <span data-ttu-id="29ec4-113">Além disso, agora é possível ter as solicitações GRANTED e WAITING exibidas para o mesmo recurso, o que não era possível no [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29ec4-113">Also, it is now possible to have GRANTED and WAITING requests displayed for the same resource, which was not possible in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="29ec4-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="29ec4-114">Permissions</span></span>  
 <span data-ttu-id="29ec4-115">, é necessário ter permissão VIEW SERVER STATE no servidor.</span><span class="sxs-lookup"><span data-stu-id="29ec4-115">Requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ec4-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29ec4-116">See Also</span></span>  
 <span data-ttu-id="29ec4-117">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="29ec4-117">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="29ec4-118">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="29ec4-118">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
