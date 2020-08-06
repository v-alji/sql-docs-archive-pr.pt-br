---
title: Opções de configuração de servidor access check cache | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- access check cache option
- access check cache bucket count
- access check cache quota
ms.assetid: 0a992ea8-3ec6-4a4d-97b5-460ae7326247
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feed895eeb7b11b4c41c51c4c26859a1057d2733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568790"
---
# <a name="access-check-cache-server-configuration-options"></a><span data-ttu-id="f3043-102">Opções access check cache de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="f3043-102">access check cache Server Configuration Options</span></span>
<span data-ttu-id="f3043-103">Quando objetos de banco de dados são acessados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a verificação de acesso é armazenada em cache em uma estrutura interna chamada **cache de resultado de verificação de acesso**.</span><span class="sxs-lookup"><span data-stu-id="f3043-103">When database objects are accessed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the access check is cached in an internal structure called the **access check result cache**.</span></span> 
  
<span data-ttu-id="f3043-104">A opção **número de buckets do cache de verificação de acesso** controla o número de buckets de hash que são usados para o cache de resultados de verificação de acesso.</span><span class="sxs-lookup"><span data-stu-id="f3043-104">The **access check cache bucket count** option controls the number of hash buckets that are used for the access check result cache.</span></span> 

<span data-ttu-id="f3043-105">A opção **cota do cache de verificação de acesso** controla o número de entradas que são armazenadas no cache de resultados de verificação de acesso.</span><span class="sxs-lookup"><span data-stu-id="f3043-105">The **access check cache quota** option controls the number of entries that are stored in the access check result cache.</span></span> <span data-ttu-id="f3043-106">Quando o número máximo de entradas é alcançado, as entradas mais antigas são removidas do cache de resultados de verificação de acesso.</span><span class="sxs-lookup"><span data-stu-id="f3043-106">When the maximum number of entries is reached, the oldest entries are removed from the access check result cache.</span></span>
  
<span data-ttu-id="f3043-107">Os valores padrão de 0 indicam aquele o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está gerenciando essas opções.</span><span class="sxs-lookup"><span data-stu-id="f3043-107">The default values of 0 indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is managing these options.</span></span> <span data-ttu-id="f3043-108">De [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] até [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] , os valores padrão são convertidos para as seguintes configurações internas:</span><span class="sxs-lookup"><span data-stu-id="f3043-108">From [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] through [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], the default values translate to the following internal configurations:</span></span>
-   <span data-ttu-id="f3043-109">Para a contagem de buckets de cache de verificação de acesso, o valor 0 define um valor padrão de 256 buckets para arquitetura x86 e 2.048 buckets para arquiteturas x64 e IA-64.</span><span class="sxs-lookup"><span data-stu-id="f3043-109">For access check cache bucket count, the value 0 sets a default value of 256 buckets for x86 architecture, and 2,048 buckets for x64 and IA-64 architectures.</span></span>
-   <span data-ttu-id="f3043-110">Para a cota de cache de verificação de acesso, o valor 0 define um valor padrão de 1.024 entradas para a arquitetura x86 e 28.192.048 buckets para arquiteturas x64 e IA-64.</span><span class="sxs-lookup"><span data-stu-id="f3043-110">For access check cache quota, the value 0 sets a default value of 1,024 entries for x86 architecture, and 28,192,048 buckets for x64 and IA-64 architectures.</span></span>

<span data-ttu-id="f3043-111">Em circunstâncias raras, o desempenho pode ser melhorado alterando essas opções.</span><span class="sxs-lookup"><span data-stu-id="f3043-111">In rare circumstances, performance can be improved by changing these options.</span></span> <span data-ttu-id="f3043-112">Por exemplo, talvez você queira reduzir o tamanho do cache de resultados de verificação de acesso se for usada muita memória.</span><span class="sxs-lookup"><span data-stu-id="f3043-112">For example, you may want to reduce the size of the access check result cache if too much memory is used.</span></span> <span data-ttu-id="f3043-113">Ou, talvez você queira aumentar o tamanho do cache de resultados de verificação de acesso se tiver um alto uso da CPU quando as permissões forem recalculadas.</span><span class="sxs-lookup"><span data-stu-id="f3043-113">Or, you may want to increase the size of the access check result cache if you experience high CPU usage when permissions are recalculated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3043-114">A Microsoft recomenda a alteração dessas opções apenas quando orientadas pelos Serviços de Atendimento ao Cliente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f3043-114">Microsoft recommends only changing these options when directed by Microsoft Customer Support Services.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f3043-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f3043-115">See Also</span></span>  
 <span data-ttu-id="f3043-116">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3043-116">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="f3043-117">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f3043-117">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
