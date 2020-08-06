---
title: Remover vários servidores de destino de um servidor mestre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
- multiple target server defections
ms.assetid: 61a3713b-403a-4806-bfc4-66db72ca1156
author: stevestein
ms.author: sstein
ms.openlocfilehash: b31a8bc38968733de0a23f67a71772721c8baedd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680294"
---
# <a name="defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="d95fe-102">Defect Multiple Target Servers from a Master Server</span><span class="sxs-lookup"><span data-stu-id="d95fe-102">Defect Multiple Target Servers from a Master Server</span></span>
  <span data-ttu-id="d95fe-103">Este tópico descreve como remover vários servidores de destino de uma configuração de administração multisservidor no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d95fe-103">This topic describes how to defect multiple target servers from a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d95fe-104">Execute este procedimento a partir do servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="d95fe-104">Run this procedure from the master server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d95fe-105">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d95fe-105">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="d95fe-106">Para remover vários servidores de destino de um servidor mestre</span><span class="sxs-lookup"><span data-stu-id="d95fe-106">To defect multiple target servers from a master server</span></span>  
  
1.  <span data-ttu-id="d95fe-107">No **Pesquisador de Objetos**, expanda um servidor que esteja configurado como servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="d95fe-107">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="d95fe-108">Clique com o botão direito do mouse em **SQL Server Agent**, aponte para **Administração Multisservidor**e clique em **Gerenciar Servidores de Destino**.</span><span class="sxs-lookup"><span data-stu-id="d95fe-108">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="d95fe-109">Clique em **Postar Instruções**e, na lista **Tipo de instrução** , selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="d95fe-109">Click **Post Instructions**, and then in the **Instruction type** list, select **Defect**.</span></span>  
  
4.  <span data-ttu-id="d95fe-110">Em **Destinatários**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="d95fe-110">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="d95fe-111">Clique em **Todos os servidores de destino** para remover todos os servidores de destino desse servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="d95fe-111">Click **All target servers** to defect all target servers of this master server.</span></span> <span data-ttu-id="d95fe-112">Use esta opção se quiser desinstalar completamente a configuração de administração multisservidor atual.</span><span class="sxs-lookup"><span data-stu-id="d95fe-112">Use this option if you want to completely uninstall the current multiserver administration configuration.</span></span>  
  
    -   <span data-ttu-id="d95fe-113">Clique em **Estes servidores de destino**e então clique na caixa **Selecionar** correspondente aos servidores de destino que devem ser removidos desse servidor mestre, para remover apenas alguns deles.</span><span class="sxs-lookup"><span data-stu-id="d95fe-113">Click **These target servers**, and then click the corresponding **Select** box, to defect some, but not all, target servers of this master server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d95fe-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d95fe-114">See Also</span></span>  
 <span data-ttu-id="d95fe-115">[Criar um ambiente multisservidor](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="d95fe-115">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="d95fe-116">[Administração automatizada em toda a empresa](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="d95fe-116">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="d95fe-117">Defect a Target Server from a Master Server</span><span class="sxs-lookup"><span data-stu-id="d95fe-117">Defect a Target Server from a Master Server</span></span>](defect-a-target-server-from-a-master-server.md)  
  
  
