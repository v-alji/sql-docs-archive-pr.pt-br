---
title: Opção de configuração de servidor clr enabled | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- assemblies [CLR integration], verifying can run
- clr enabled option
ms.assetid: 0722d382-8fd3-4fac-b4a8-cd2b7a7e0293
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b83cd0e00bdd32c8b44667209544c8e81b1e90c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569654"
---
# <a name="clr-enabled-server-configuration-option"></a><span data-ttu-id="b8de7-102">Opção clr enabled de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="b8de7-102">clr enabled Server Configuration Option</span></span>
  <span data-ttu-id="b8de7-103">Use a opção clr habilitado para especificar se assemblies de usuário podem ser executados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8de7-103">Use the clr enabled option to specify whether user assemblies can be run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b8de7-104">A opção clr enabled fornece os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="b8de7-104">The clr enabled option provides the following values.</span></span>  
  
|<span data-ttu-id="b8de7-105">Valor</span><span class="sxs-lookup"><span data-stu-id="b8de7-105">Value</span></span>|<span data-ttu-id="b8de7-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="b8de7-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b8de7-107">0</span><span class="sxs-lookup"><span data-stu-id="b8de7-107">0</span></span>|<span data-ttu-id="b8de7-108">Execução de assembly não permitida no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8de7-108">Assembly execution not allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="b8de7-109">1</span><span class="sxs-lookup"><span data-stu-id="b8de7-109">1</span></span>|<span data-ttu-id="b8de7-110">Execução de assembly permitida no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8de7-110">Assembly execution allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
 <span data-ttu-id="b8de7-111">Servidores WOW64 devem ser reiniciados antes das alterações nessa configuração entrarem em vigor.</span><span class="sxs-lookup"><span data-stu-id="b8de7-111">WOW64 servers must be restarted before the changes to this setting will take effect.</span></span> <span data-ttu-id="b8de7-112">A reinicialização não é necessária para outros tipos de servidores.</span><span class="sxs-lookup"><span data-stu-id="b8de7-112">Restart is not required for other server types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8de7-113">Quando RECONFIGURE é executado e o valor de execução da opção clr ativado é alterado de 1 para 0, todos os domínios de aplicativo que contêm assemblies de usuário são descarregados imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b8de7-113">When RECONFIGURE is run and the run value of the clr enabled option is changed from 1 to 0, all application domains containing user assemblies are immediately unloaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8de7-114">Não há suporte para a execução de CLR (common language runtime) com lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="b8de7-114">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="b8de7-115">Desabilite uma das duas opções: “clr enabled” ou “lightweight pooling”.</span><span class="sxs-lookup"><span data-stu-id="b8de7-115">Disable one of two options: "clr enabled" or "lightweight pooling.</span></span> <span data-ttu-id="b8de7-116">Os recursos que dependem de CLR e que não funcionam corretamente no modo fibra incluem o tipo de dados `hierarchy`, replicação e Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="b8de7-116">Features that rely upon CLR and that do not work properly in fiber mode include the `hierarchy` data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8de7-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b8de7-117">Example</span></span>  
 <span data-ttu-id="b8de7-118">O exemplo a seguir primeiro mostra a configuração atual da opção clr enabled e, em seguida, habilita a opção configurando o valor da opção como 1.</span><span class="sxs-lookup"><span data-stu-id="b8de7-118">The following example first displays the current setting of the clr enabled option and then enables the option by setting the option value to 1.</span></span> <span data-ttu-id="b8de7-119">Para desabilitar a opção, defina o valor para 0.</span><span class="sxs-lookup"><span data-stu-id="b8de7-119">To disable the option, set the value to 0.</span></span>  
  
```  
EXEC sp_configure 'clr enabled';  
EXEC sp_configure 'clr enabled' , '1';  
RECONFIGURE;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8de7-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b8de7-120">See Also</span></span>  
 <span data-ttu-id="b8de7-121">[Opção lightweight pooling de configuração de Servidor](lightweight-pooling-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="b8de7-121">[lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md) </span></span>  
 <span data-ttu-id="b8de7-122">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b8de7-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="b8de7-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b8de7-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="b8de7-124">Opção lightweight pooling de configuração de Servidor</span><span class="sxs-lookup"><span data-stu-id="b8de7-124">lightweight pooling Server Configuration Option</span></span>](lightweight-pooling-server-configuration-option.md)  
  
  
