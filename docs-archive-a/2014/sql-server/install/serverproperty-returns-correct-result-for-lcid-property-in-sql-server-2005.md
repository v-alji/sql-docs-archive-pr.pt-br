---
title: SERVERPROPERTY retorna o resultado correto para a propriedade LCID no SQL Server 2005 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SERVERPROPERTY function
ms.assetid: 833a2fc9-b480-4697-aa7b-9677e78ee0b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebb125a86e6e30f2c3638004593da7657f02f1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680761"
---
# <a name="serverproperty-returns-correct-result-for-lcid-property-in-sql-server-2005"></a><span data-ttu-id="dbc7c-102">SERVERPROPERTY retorna resultado correto para a propriedade LCID no SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="dbc7c-102">SERVERPROPERTY returns correct result for LCID property in SQL Server 2005</span></span>
  <span data-ttu-id="dbc7c-103">Quando SERVERPROPERTY('LCID') é executado em servidores de ordenação primária, a função retorna o LCID (identificador de localidade) do Windows que corresponde à ordenação do servidor.</span><span class="sxs-lookup"><span data-stu-id="dbc7c-103">When SERVERPROPERTY('LCID') is run on binary collation servers, the function returns the Windows locale identifier (LCID) that corresponds to the collation of the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dbc7c-104">No caso de arquivos em lote ou de rastreamento que contêm referências a SERVERPROPERTY ('LCID') e que são executados em outras instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o Supervisor de Atualização detectará essa alteração de comportamento somente se outras instâncias tiverem a mesma ordenação que a instância atual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbc7c-104">For batch and trace files that contain references to SERVERPROPERTY ('LCID') and are run on other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Upgrade Advisor will detect this behavior change only if the other instances have the same collation as the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="dbc7c-105">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="dbc7c-105">Corrective Action</span></span>  
 <span data-ttu-id="dbc7c-106">Modifique os aplicativos para que estejam preparados para que SERVERPROPERTY ('LCID') retorne o LCDI do Windows que corresponde à ordenação do servidor.</span><span class="sxs-lookup"><span data-stu-id="dbc7c-106">Modify applications to expect SERVERPROPERTY('LCID') to return the Windows LCID that corresponds to the collation of the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc7c-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dbc7c-107">See Also</span></span>  
 <span data-ttu-id="dbc7c-108">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="dbc7c-108">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="dbc7c-109">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="dbc7c-109">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
