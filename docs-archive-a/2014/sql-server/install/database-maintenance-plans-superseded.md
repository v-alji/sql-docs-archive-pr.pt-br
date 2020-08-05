---
title: Planos de manutenção de banco de dados substituídos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- suspended database maintenance plans
- database maintenance plans [SQL Server Agent]
- maintenance plans [SQL Server Agent]
ms.assetid: efac127c-6c81-4c7a-a6c4-9aae5d15545d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3aea75cc4ecc94ccbaeb1f35cecd0b18ff3a65ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569046"
---
# <a name="database-maintenance-plans-superseded"></a><span data-ttu-id="7d227-102">Planos de manutenção de banco de dados substituídos</span><span class="sxs-lookup"><span data-stu-id="7d227-102">Database maintenance plans superseded</span></span>
    
## <a name="component"></a><span data-ttu-id="7d227-103">Componente</span><span class="sxs-lookup"><span data-stu-id="7d227-103">Component</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="7d227-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agente do</span><span class="sxs-lookup"><span data-stu-id="7d227-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="7d227-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d227-105">Description</span></span>  
 <span data-ttu-id="7d227-106">Os planos de manutenção de banco de dados são atualizados e continuam a funcionar.</span><span class="sxs-lookup"><span data-stu-id="7d227-106">Existing database maintenance plans are upgraded and continue to work.</span></span> <span data-ttu-id="7d227-107">Porém, você não poderá criar novos planos de manutenção de banco de dados usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d227-107">However, you will not be able to create new database maintenance plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="7d227-108">Para exibir os planos de manutenção no Pesquisador de Objetos, expanda Gerenciamento e, em seguida, Herdado.</span><span class="sxs-lookup"><span data-stu-id="7d227-108">To view the maintenance plans in Object Explorer, expand Management, and then expand Legacy.</span></span> <span data-ttu-id="7d227-109">Você pode migrar planos de manutenção de banco de dados existentes para o novo formato selecionando **migrar** no menu de contexto de qualquer plano de manutenção de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7d227-109">You can migrate existing database maintenance plans to the new format by selecting **Migrate** from the context menu for any database maintenance plan.</span></span> <span data-ttu-id="7d227-110">Como o novo recurso de plano de manutenção não é uma substituição direta para os planos de manutenção de banco de dados, existe a possibilidade de perder algumas funcionalidades após a migração.</span><span class="sxs-lookup"><span data-stu-id="7d227-110">Because the new maintenance plan feature is not a direct replacement of database maintenance plans, some functionality might be lost after migration.</span></span> <span data-ttu-id="7d227-111">A migração de um plano de manutenção de banco de dados não exclui o plano anterior, portanto você pode testar sua funcionalidade como um plano de manutenção antes de remover o plano anterior.</span><span class="sxs-lookup"><span data-stu-id="7d227-111">Migrating a database maintenance plan does not delete the old plan, so you can test its functionality as a maintenance plan before removing the old plan.</span></span>  
  
 <span data-ttu-id="7d227-112">Não há mais suporte para os seguintes recursos dentro dos planos de manutenção de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="7d227-112">The following features are no longer supported within database maintenance plans:</span></span>  
  
-   <span data-ttu-id="7d227-113">Envio de logs</span><span class="sxs-lookup"><span data-stu-id="7d227-113">Log shipping</span></span>  
  
-   <span data-ttu-id="7d227-114">A opção **tentar reparar problemas secundários** da tarefa de **verificação de integridade do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="7d227-114">The **Attempt to repair any minor problems** option of the **Database Integrity Check** task</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="7d227-115">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="7d227-115">Corrective Action</span></span>  
 <span data-ttu-id="7d227-116">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] impede que o envio de logs seja incluído em um plano de manutenção do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7d227-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prevents log shipping from being included in a database maintenance plan.</span></span> <span data-ttu-id="7d227-117">Para obter mais informações, consulte o tópico ‘Envio de logs’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d227-117">For more information, see "Log Shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
