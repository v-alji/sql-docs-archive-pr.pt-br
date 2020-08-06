---
title: Opção de configuração de servidor lightweight pooling | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default lightweight pooling
- decreasing overhead
- lightweight pooling option
- system overhead [SQL Server]
- performance [SQL Server], lightweight pooling
- context switching [SQL Server], lightweight pooling option
- excessive context switching [SQL Server]
- reducing overhead
- overhead [SQL Server]
ms.assetid: 2dc11b61-d065-4126-8e00-acf40390f9fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 549ff7451a31b48459b5a290b94ad406c3768a91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574904"
---
# <a name="lightweight-pooling-server-configuration-option"></a><span data-ttu-id="804ab-102">Opção lightweight pooling de configuração de Servidor</span><span class="sxs-lookup"><span data-stu-id="804ab-102">lightweight pooling Server Configuration Option</span></span>
  <span data-ttu-id="804ab-103">Use a opção **lightweight pooling** para fornecer meios para reduzir a sobrecarga do sistema associada à alternância excessiva de contexto que ocorre às vezes em ambientes SMP (multiprocessamento simétrico).</span><span class="sxs-lookup"><span data-stu-id="804ab-103">Use the **lightweight pooling** option to provide a means of reducing the system overhead associated with the excessive context switching sometimes seen in symmetric multiprocessing (SMP) environments.</span></span> <span data-ttu-id="804ab-104">Quando há alternância excessiva de contexto, o lightweight pooling pode fornecer melhor transferência realizando a alternância de contexto embutido, ajudando assim a reduzir as transições de chamadas entre o usuário e o kernel.</span><span class="sxs-lookup"><span data-stu-id="804ab-104">When excessive context switching is present, lightweight pooling can provide better throughput by performing the context switching inline, thus helping to reduce user/kernel ring transitions.</span></span>  
  
 <span data-ttu-id="804ab-105">O modo fibra foi projetado para determinadas situações nas quais a alternância de contexto dos trabalhadores UMS são o gargalo crítico no desempenho.</span><span class="sxs-lookup"><span data-stu-id="804ab-105">Fiber mode is intended for certain situations in which the context switching of the UMS workers are the critical bottleneck in performance.</span></span> <span data-ttu-id="804ab-106">Como isso é raro, o modo fibra raramente aumenta o desempenho ou a escalabilidade no sistema típico.</span><span class="sxs-lookup"><span data-stu-id="804ab-106">Because this is rare, fiber mode rarely enhances performance or scalability on the typical system.</span></span> <span data-ttu-id="804ab-107">A alternância de contexto aprimorada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] também reduziu a necessidade do modo fibra.</span><span class="sxs-lookup"><span data-stu-id="804ab-107">Improved context switching in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] has also reduced the need for fiber mode.</span></span> <span data-ttu-id="804ab-108">Não recomendamos o uso de agendamento do modo fibra para operação de rotina.</span><span class="sxs-lookup"><span data-stu-id="804ab-108">We do not recommend that you use fiber mode scheduling for routine operation.</span></span> <span data-ttu-id="804ab-109">Isso porque pode diminuir o desempenho ao inibir os benefícios comuns da alternância de contexto, e como alguns componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usam o TLS (Armazenamento de Thread Local) ou objetos de propriedade de thread, como mutexes (um tipo de objeto kernel de Win32), não funcionam corretamente no modo fibra.</span><span class="sxs-lookup"><span data-stu-id="804ab-109">This is because it can decrease performance by inhibiting the regular benefits of context switching, and because some components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that use Thread Local Storage (TLS) or thread-owned objects, such as mutexes (a type of Win32 kernel object), cannot function correctly in fiber mode.</span></span>  
  
 <span data-ttu-id="804ab-110">Definir **lightweight pooling** como 1 faz com que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alterne para a programação de modo fibra.</span><span class="sxs-lookup"><span data-stu-id="804ab-110">Setting **lightweight pooling** to 1 causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to switch to fiber mode scheduling.</span></span> <span data-ttu-id="804ab-111">O valor padrão desta opção é 0.</span><span class="sxs-lookup"><span data-stu-id="804ab-111">The default value for this option is 0.</span></span>  
  
 <span data-ttu-id="804ab-112">A opção **lightweight pooling** é uma opção avançada.</span><span class="sxs-lookup"><span data-stu-id="804ab-112">The **lightweight pooling** option is an advanced option.</span></span> <span data-ttu-id="804ab-113">Se você estiver usando o procedimento armazenado do sistema **sp_configure** para alterar a configuração, será possível alterar a opção **lightweight pooling** apenas quando **show advanced options** estiver definida como 1.</span><span class="sxs-lookup"><span data-stu-id="804ab-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change **lightweight pooling** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="804ab-114">A configuração terá efeito depois que o servidor for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="804ab-114">The setting takes effect after the server is restarted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="804ab-115">Não há suporte para a opção lightweight pooling no [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 e no [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span><span class="sxs-lookup"><span data-stu-id="804ab-115">Lightweight pooling is not supported for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span></span> [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] <span data-ttu-id="804ab-116">fornece suporte completo à lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="804ab-116">provides full support for lightweight pooling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="804ab-117">Não há suporte para a execução de CLR (common language runtime) com lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="804ab-117">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="804ab-118">Desabilite uma das duas opções: “clr enabled” ou “lightweight pooling”.</span><span class="sxs-lookup"><span data-stu-id="804ab-118">Disable one of two options: "clr enabled" or "lightweight pooling".</span></span> <span data-ttu-id="804ab-119">Alguns dos recursos que dependem de CLR e não funcionam corretamente no modo fibra incluem o tipo de dados de hierarquia, a replicação e Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="804ab-119">Features that rely upon CLR and that do not work properly in fiber mode include the hierarchy data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="804ab-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="804ab-120">See Also</span></span>  
 <span data-ttu-id="804ab-121">[Opção clr enabled de configuração de servidor](clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="804ab-121">[clr enabled Server Configuration Option](clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="804ab-122">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="804ab-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="804ab-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="804ab-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="804ab-124">Opção de configuração do servidor clr enabled</span><span class="sxs-lookup"><span data-stu-id="804ab-124">clr enabled Server Configuration Option</span></span>](clr-enabled-server-configuration-option.md)  
  
  
