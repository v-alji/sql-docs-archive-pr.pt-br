---
title: Opção de configuração de servidor allow updates | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- allow updates option
ms.assetid: 3967c3ed-280a-4de8-a2ce-393e82745a7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d7e3ede317509a2044be90635db46e30a932af66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575350"
---
# <a name="allow-updates-server-configuration-option"></a><span data-ttu-id="b70ba-102">Opção allow updates de configuração de Servidor</span><span class="sxs-lookup"><span data-stu-id="b70ba-102">allow updates Server Configuration Option</span></span>
  <span data-ttu-id="b70ba-103">Essa opção ainda está presente no procedimento armazenado **sp_configure** , embora sua funcionalidade esteja indisponível no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b70ba-103">This option is still present in the **sp_configure** stored procedure, although its functionality is unavailable in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b70ba-104">A configuração não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="b70ba-104">The setting has no effect.</span></span> <span data-ttu-id="b70ba-105">Não serão aceitas atualizações diretas para as tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="b70ba-105">Direct updates to the system tables are not supported.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="b70ba-106">A alteração da opção **permitir atualizações** fará com que a instrução RECONFIGURE falhe.</span><span class="sxs-lookup"><span data-stu-id="b70ba-106">Changing the **allow updates** option will cause the RECONFIGURE statement to fail.</span></span> <span data-ttu-id="b70ba-107">Alterações na opção **permitir atualizações** devem ser removidas de todos os scripts.</span><span class="sxs-lookup"><span data-stu-id="b70ba-107">Changes to the **allow updates** option should be removed from all scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b70ba-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b70ba-108">See Also</span></span>  
 [<span data-ttu-id="b70ba-109">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b70ba-109">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
