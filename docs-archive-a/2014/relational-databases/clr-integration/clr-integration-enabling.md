---
title: Habilitando a integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- clr enabled option
- common language runtime [SQL Server], enabling
ms.assetid: eb3e9c64-7486-42e7-baf6-c956fb311a2c
author: rothja
ms.author: jroth
ms.openlocfilehash: d7187906f1376deb81ca7ff4770af7b12b63c022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682274"
---
# <a name="enabling-clr-integration"></a><span data-ttu-id="93652-102">Habilitando integração CLR</span><span class="sxs-lookup"><span data-stu-id="93652-102">Enabling CLR Integration</span></span>
  <span data-ttu-id="93652-103">O recurso de integração CLR (common language runtime) está desativado por padrão, e deve ser habilitado para usar objetos implementados com a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="93652-103">The common language runtime (CLR) integration feature is off by default, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="93652-104">Para habilitar a integração CLR, use a opção **CLR Enabled** do procedimento armazenado **sp_configure** :</span><span class="sxs-lookup"><span data-stu-id="93652-104">To enable CLR integration, use the **clr enabled** option of the **sp_configure** stored procedure:</span></span>  
  
```  
  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'clr enabled', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="93652-105">Você pode desabilitar a integração CLR definindo a opção **CLR Enabled** como 0.</span><span class="sxs-lookup"><span data-stu-id="93652-105">You can disable CLR integration by setting the **clr enabled** option to 0.</span></span> <span data-ttu-id="93652-106">Quando você desabilitar integração de CLR, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deixará de executar todas as rotinas de CLR e descarregará todos os domínios de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="93652-106">When you disable CLR integration, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stops executing all CLR routines and unloads all application domains.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93652-107">Para habilitar a integração CLR, você deve ter a permissão ALTER SETTINGS no nível do servidor, que é mantida implicitamente por membros das funções de servidor fixas **sysadmin** e **ServerAdmin** .</span><span class="sxs-lookup"><span data-stu-id="93652-107">To enable CLR integration, you must have ALTER SETTINGS server level permission, which is implicitly held by members of the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93652-108">Computadores configurados com grandes quantidades de memória e um número grande de processadores podem falhar ao carregar o recurso de integração CLR do SQL Server na inicialização do servidor.</span><span class="sxs-lookup"><span data-stu-id="93652-108">Computers configured with large amounts of memory and a large number of processors may fail to load the CLR integration feature of SQL Server when starting the server.</span></span> <span data-ttu-id="93652-109">Para resolver esse problema, inicie o servidor usando a opção de inicialização de serviço **-gmemory_to_reserve** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e especifique um valor de memória grande o suficiente.</span><span class="sxs-lookup"><span data-stu-id="93652-109">To address this issue, start the server by using the **-gmemory_to_reserve**[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service startup option, and specify a memory value large enough.</span></span> <span data-ttu-id="93652-110">Para obter mais informações, consulte [Opções de inicialização do serviço Mecanismo de Banco de Dados](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="93652-110">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93652-111">Não há suporte para a execução de CLR (common language runtime) com lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="93652-111">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="93652-112">Antes de habilitar integração CLR, você deve desabilitar o lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="93652-112">Before enabling CLR integration, you must disable lightweight pooling.</span></span> <span data-ttu-id="93652-113">Para saber mais, veja [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="93652-113">For more information, see [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93652-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="93652-114">See Also</span></span>  
 <span data-ttu-id="93652-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93652-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="93652-116">[Opção clr enabled de configuração de servidor](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="93652-116">[clr enabled Server Configuration Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="93652-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93652-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="93652-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93652-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="93652-119">Funções de nível de servidor</span><span class="sxs-lookup"><span data-stu-id="93652-119">Server-Level Roles</span></span>](../security/authentication-access/server-level-roles.md)  
  
  
