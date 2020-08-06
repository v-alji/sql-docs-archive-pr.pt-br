---
title: Opção de configuração de servidor disallow results from triggers | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], result sets
- result sets [SQL Server], triggers
- disallow results from triggers option
ms.assetid: 47149073-307d-47a5-b7d2-66a737d3231d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f162a6e06706561d861bfc54a1ae4027f2c3466e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678289"
---
# <a name="disallow-results-from-triggers-server-configuration-option"></a><span data-ttu-id="1b94f-102">Opção de configuração de servidor disallow results from triggers</span><span class="sxs-lookup"><span data-stu-id="1b94f-102">disallow results from triggers Server Configuration Option</span></span>
  <span data-ttu-id="1b94f-103">Use a opção **rejeitar resultados dos gatilhos** para controlar se os gatilhos retornam conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="1b94f-103">Use the **disallow results from triggers** option to control whether triggers return result sets.</span></span> <span data-ttu-id="1b94f-104">Os gatilhos que retornam conjuntos de resultados podem causar um comportamento inesperado em aplicativos que não são projetados para trabalhar com eles.</span><span class="sxs-lookup"><span data-stu-id="1b94f-104">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="1b94f-105">Recomendamos que você defina esse valor como 1.</span><span class="sxs-lookup"><span data-stu-id="1b94f-105">We recommend that you set this value to 1.</span></span>  
  
 <span data-ttu-id="1b94f-106">Ao definir como 1, a opção **rejeitar resultados dos gatilhos** será definida como ON.</span><span class="sxs-lookup"><span data-stu-id="1b94f-106">When set to 1, the **disallow results from triggers** option is set to ON.</span></span> <span data-ttu-id="1b94f-107">A configuração padrão para esta opção é 0 (OFF).</span><span class="sxs-lookup"><span data-stu-id="1b94f-107">The default setting for this option is 0 (OFF).</span></span> <span data-ttu-id="1b94f-108">Se esta opção estiver definida para 1 (ON), qualquer tentativa feita por um gatilho para retornar um conjunto de resultados falhará e o usuário receberá a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="1b94f-108">If this option is set to 1 (ON), any attempt by a trigger to return a result set fails, and the user receives the following error message:</span></span>  
  
 <span data-ttu-id="1b94f-109">"Mensagem 524, Nível 16, Estado 1, Procedimento \<Procedure Name>, Linha \<Line#></span><span class="sxs-lookup"><span data-stu-id="1b94f-109">"Msg 524, Level 16, State 1, Procedure \<Procedure Name>, Line \<Line#></span></span>  
  
 <span data-ttu-id="1b94f-110">"Um gatilho retornou um conjunto de resultados e a opção do servidor 'disallow_results_from_triggers' é verdadeira."</span><span class="sxs-lookup"><span data-stu-id="1b94f-110">"A trigger returned a resultset and the server option 'disallow_results_from_triggers' is true."</span></span>  
  
 <span data-ttu-id="1b94f-111">A opção **disallow results from triggers** é aplicada no nível de instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e determinará o comportamento de todos os gatilhos existentes na instância.</span><span class="sxs-lookup"><span data-stu-id="1b94f-111">The **disallow results from triggers** option is applied at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance level, and it will determine behavior for all existing triggers within the instance.</span></span>  
  
 <span data-ttu-id="1b94f-112">A opção **rejeitar resultados dos gatilhos** é uma opção avançada.</span><span class="sxs-lookup"><span data-stu-id="1b94f-112">The **disallow results from triggers** option is an advanced option.</span></span> <span data-ttu-id="1b94f-113">Se você estiver usando o procedimento armazenado no sistema **sp_configure** para alterar a configuração, é possível alterar a opção rejeitar resultados dos gatilhos somente quando **mostrar opções avançadas** estiver definida como 1.</span><span class="sxs-lookup"><span data-stu-id="1b94f-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change disallow results from triggers only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="1b94f-114">A configuração entra em vigor imediatamente sem a reinicialização do servidor.</span><span class="sxs-lookup"><span data-stu-id="1b94f-114">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b94f-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1b94f-115">See Also</span></span>  
 <span data-ttu-id="1b94f-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1b94f-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="1b94f-117">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1b94f-117">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="1b94f-118">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b94f-118">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
