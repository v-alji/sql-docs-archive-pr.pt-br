---
title: Alterações no comportamento de sinalizadores de rastreamento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- trace flags [SQL Server], behavior changes
ms.assetid: d739df96-2659-4383-8e10-194657632526
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11d71e8401f6b870aaeb3f64f4145b509e3a3fe0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573518"
---
# <a name="changes-to-behavior-of-trace-flags"></a><span data-ttu-id="a5f0a-102">Alterações no comportamento de sinalizadores de rastreamento</span><span class="sxs-lookup"><span data-stu-id="a5f0a-102">Changes to behavior of trace flags</span></span>
  <span data-ttu-id="a5f0a-103">Sinalizadores de rastreamento globais definidos por uma sessão afetam outras sessões imediatamente.</span><span class="sxs-lookup"><span data-stu-id="a5f0a-103">Global trace flags set by a session take effect in other sessions immediately.</span></span> <span data-ttu-id="a5f0a-104">Alguns sinalizadores de rastreamento do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] não existem no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5f0a-104">Some trace flags from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] do not exist in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="a5f0a-105">Componente</span><span class="sxs-lookup"><span data-stu-id="a5f0a-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a5f0a-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5f0a-106">Description</span></span>  
 <span data-ttu-id="a5f0a-107">Recomendamos que você desabilite todos os sinalizadores de rastreamento antes de atualizar.</span><span class="sxs-lookup"><span data-stu-id="a5f0a-107">We recommend that you disable all trace flags before you upgrade.</span></span> <span data-ttu-id="a5f0a-108">Os sinalizadores de rastreamento que modificam os modos de disponibilidade ou recuperação do banco de dados podem impedir que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] atualize com êxito sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5f0a-108">Trace flags that modify the database availability or recovery modes might prevent the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] from successfully upgrading your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a5f0a-109">Você poderá habilitar os sinalizadores de rastreamento depois de verificar se eles são necessários e continuam válidos no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5f0a-109">You can enable the trace flags after you verify that the trace flags are required and are still valid in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a5f0a-110">Se precisar habilitar novamente esses sinalizadores de rastreamento, será necessário fazer testes adicionais em sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5f0a-110">If you must re-enable trace flags, you should perform additional tests on your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a5f0a-111">O [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oferece suporte a sinalizadores de rastreamento no nível de sessão e globais.</span><span class="sxs-lookup"><span data-stu-id="a5f0a-111">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supports global and session level trace flags.</span></span> <span data-ttu-id="a5f0a-112">No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], os sinalizadores de rastreamento podem ser especificados tanto como locais quanto como globais usando o argumento adicional (-1) no comando DBCC TRACEON.</span><span class="sxs-lookup"><span data-stu-id="a5f0a-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], trace flags can be specified as either local or global by using an additional argument (-1) in the DBCC TRACEON command.</span></span> <span data-ttu-id="a5f0a-113">Se esse argumento não for especificado, o valor padrão será local.</span><span class="sxs-lookup"><span data-stu-id="a5f0a-113">If this argument is not specified, the default value is local.</span></span>  
  
 <span data-ttu-id="a5f0a-114">Além disso, no [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] , um sinalizador de rastreamento definido na sessão a não tem efeito automaticamente em uma sessão B já existente. Em vez disso, esse sinalizador de rastreamento entra em vigor somente após a primeira vez que qualquer sinalizador de rastreamento é definido na sessão B. Esse comportamento não é determinístico no [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] e é determinístico no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e em versões posteriores, em que os sinalizadores de rastreamento globais definidos na sessão A são definidos imediatamente em outras sessões simultâneas.</span><span class="sxs-lookup"><span data-stu-id="a5f0a-114">Also, in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a trace flag set in session A does not automatically take effect in an already existing session B. Instead, this trace flag takes effect only after the first time any trace flag is set in session B. This behavior is nondeterministic in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] and is deterministic in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, where global trace flags set in session A are set immediately in other concurrent sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f0a-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a5f0a-115">See Also</span></span>  
 <span data-ttu-id="a5f0a-116">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a5f0a-116">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a5f0a-117">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="a5f0a-117">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
