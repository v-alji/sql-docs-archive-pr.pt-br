---
title: Manter o valor padrão da opção de configuração de bloqueios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: f214f05b-5f0b-4786-b2ad-b8b4b6e58d72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a1d1dcf82d9cd0ef8ef2c15cb68ef78b53a8a54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569973"
---
# <a name="keep-the-locks-configuration-option-default-value"></a><span data-ttu-id="e6413-102">Manutenção do valor padrão da opção configuração de bloqueios</span><span class="sxs-lookup"><span data-stu-id="e6413-102">Keep the Locks Configuration Option Default Value</span></span>
  <span data-ttu-id="e6413-103">Esta regra verifica o valor da opção de configuração de bloqueios.</span><span class="sxs-lookup"><span data-stu-id="e6413-103">This rule checks the value of the locks configuration option.</span></span> <span data-ttu-id="e6413-104">Esta opção determina o número máximo de bloqueios disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e6413-104">This option determines the maximum number of available locks.</span></span> <span data-ttu-id="e6413-105">Isto limita a quantidade de memória que o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usa para bloqueios.</span><span class="sxs-lookup"><span data-stu-id="e6413-105">This limits how much memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for locks.</span></span> <span data-ttu-id="e6413-106">A configuração padrão em 0 permite que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] aloque e desaloque as estruturas de bloqueio de forma dinâmica, baseado nas alterações de requisitos de sistema.</span><span class="sxs-lookup"><span data-stu-id="e6413-106">The default setting of 0 enables the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically based on changing system requirements.</span></span>  
  
 <span data-ttu-id="e6413-107">Se os bloqueios forem diferentes de zero, os trabalhos de lote pararão e a mensagem "fora de bloqueios" de erro será gerada se o valor especificado for excedido.</span><span class="sxs-lookup"><span data-stu-id="e6413-107">If locks is nonzero, batch jobs will stop, and an "out of locks" error message will be generated, if the value specified is exceeded.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="e6413-108">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="e6413-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="e6413-109">Use o procedimento armazenado de sistema sp_configure para alterar o valor dos bloqueios para sua configuração padrão usando a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="e6413-109">Use the sp_configure system stored procedure to change the value of locks to its default setting by using the following statement:</span></span>  
  
```  
EXEC sp_configure 'locks', 0;  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="e6413-110">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="e6413-110">For More Information</span></span>  
 [<span data-ttu-id="e6413-111">Configurar a opção locks de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="e6413-111">Configure the locks Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-locks-server-configuration-option.md)  
  
 [<span data-ttu-id="e6413-112">sys.dm_tran_locks &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e6413-112">sys.dm_tran_locks &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql)  
  
 [<span data-ttu-id="e6413-113">sys.dm_os_wait_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e6413-113">sys.dm_os_wait_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-wait-stats-transact-sql)  
  
 [<span data-ttu-id="e6413-114">Artigo 271509 da Base de Dados de Conhecimento Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6413-114">Microsoft Knowledge Base article 271509</span></span>](https://go.microsoft.com/fwlink/?linkid=117788)  
  
## <a name="see-also"></a><span data-ttu-id="e6413-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e6413-115">See Also</span></span>  
 [<span data-ttu-id="e6413-116">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="e6413-116">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
