---
title: Opção de configuração de servidor in-doubt xact resolution | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- distributed transactions [SQL Server], unresolved transactions
- unresolved transactions
- in-doubt xact resolution option
ms.assetid: 3426fd32-cad2-4f2f-8ca9-e0296cc12703
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6b8db57ef2a4ee85d65e8c25de28ff7ada7994e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679528"
---
# <a name="in-doubt-xact-resolution-server-configuration-option"></a><span data-ttu-id="49f80-102">Opção de configuração de servidor in-doubt xact resolution</span><span class="sxs-lookup"><span data-stu-id="49f80-102">in-doubt xact resolution Server Configuration Option</span></span>
  <span data-ttu-id="49f80-103">Use a opção **in-doubt xact resolution** para controlar o resultado padrão de transações que o MS DTC (Coordenador de Transações Distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ) não pode resolver.</span><span class="sxs-lookup"><span data-stu-id="49f80-103">Use the **in-doubt xact resolution** option to control the default outcome of transactions that the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) is unable to resolve.</span></span> <span data-ttu-id="49f80-104">A incapacidade de resolver transações pode estar relacionada ao tempo de desligamento do MS DTC ou a um resultado de transação desconhecido no momento da recuperação.</span><span class="sxs-lookup"><span data-stu-id="49f80-104">Inability to resolve transactions may be related to the MS DTC down time or an unknown transaction outcome at the time of recovery.</span></span>  
  
 <span data-ttu-id="49f80-105">A tabela seguinte lista os possíveis valores de resultado para resolver uma transação incerta.</span><span class="sxs-lookup"><span data-stu-id="49f80-105">The following table lists the possible outcome values for resolving an in-doubt transaction.</span></span>  
  
|<span data-ttu-id="49f80-106">Valor de resultado</span><span class="sxs-lookup"><span data-stu-id="49f80-106">Outcome value</span></span>|<span data-ttu-id="49f80-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="49f80-107">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="49f80-108">0</span><span class="sxs-lookup"><span data-stu-id="49f80-108">0</span></span>|<span data-ttu-id="49f80-109">Nenhuma suposição.</span><span class="sxs-lookup"><span data-stu-id="49f80-109">No presumption.</span></span> <span data-ttu-id="49f80-110">Recuperação falhará se o MS DTC não puder resolver nenhuma transação incerta.</span><span class="sxs-lookup"><span data-stu-id="49f80-110">Recovery fails if MS DTC cannot resolve any in-doubt transactions.</span></span>|  
|<span data-ttu-id="49f80-111">1</span><span class="sxs-lookup"><span data-stu-id="49f80-111">1</span></span>|<span data-ttu-id="49f80-112">Suponha confirmação.</span><span class="sxs-lookup"><span data-stu-id="49f80-112">Presume commit.</span></span> <span data-ttu-id="49f80-113">Supõe-se que qualquer transação incerta de MS DTC esteja confirmada.</span><span class="sxs-lookup"><span data-stu-id="49f80-113">Any MS DTC in-doubt transactions are presumed to have committed.</span></span>|  
|<span data-ttu-id="49f80-114">2</span><span class="sxs-lookup"><span data-stu-id="49f80-114">2</span></span>|<span data-ttu-id="49f80-115">Suponha anulação.</span><span class="sxs-lookup"><span data-stu-id="49f80-115">Presume abort.</span></span> <span data-ttu-id="49f80-116">Supõe-se que quaisquer transações incertas de MS DTC tenham sido anuladas.</span><span class="sxs-lookup"><span data-stu-id="49f80-116">Any MS DTC in-doubt transactions are presumed to have aborted.</span></span>|  
  
 <span data-ttu-id="49f80-117">Para minimizar a possibilidade de tempo de inatividade estendido, um administrador pode configurar essa opção para supor confirmação ou anulação, como mostrado no exemplo seguinte.</span><span class="sxs-lookup"><span data-stu-id="49f80-117">To minimize the possibility of extended down time, an administrator might choose to configure this option either to presume commit or presume abort, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 2 -- presume abort  
GO  
RECONFIGURE  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="49f80-118">Como alternativa, o administrador pode deixar o padrão (nenhuma suposição) e permitir a falha da recuperação para ser alertado sobre uma falha de DTC, como mostrado no exemplo seguinte.</span><span class="sxs-lookup"><span data-stu-id="49f80-118">Alternatively, the administrator might want to leave the default (no presumption) and allow recovery to fail in order to be made aware of a DTC failure, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 1 -- presume commit  
GO  
reconfigure  
GO  
ALTER DATABASE pubs SET ONLINE -- run recovery again  
GO  
sp_configure 'in-doubt xact resolution', 0 -- back to no assumptions  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="49f80-119">A opção **in-doubt xact resolution** é uma opção avançada.</span><span class="sxs-lookup"><span data-stu-id="49f80-119">The **in-doubt xact resolution** option is an advanced option.</span></span> <span data-ttu-id="49f80-120">Se estiver usando o procedimento armazenado no sistema **sp_configure** para alterar a configuração, é possível alterar o **in-doubt xact resolution** apenas quando **mostrar opções avançadas** estiver definida como 1.</span><span class="sxs-lookup"><span data-stu-id="49f80-120">If you are using the **sp_configure** system stored procedure to change the setting, you can change **in-doubt xact resolution** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="49f80-121">A configuração entra em vigor imediatamente sem a reinicialização do servidor.</span><span class="sxs-lookup"><span data-stu-id="49f80-121">The setting takes effect immediately without a server restart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49f80-122">A configuração consistente desta opção por todas as instâncias [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] envolvidas em qualquer transação distribuída ajudará a evitar inconsistências de dados.</span><span class="sxs-lookup"><span data-stu-id="49f80-122">Consistent configuration of this option across all [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances involved in any distributed transactions will help avoid data inconsistencies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f80-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="49f80-123">See Also</span></span>  
 <span data-ttu-id="49f80-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49f80-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="49f80-125">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="49f80-125">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="49f80-126">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="49f80-126">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
