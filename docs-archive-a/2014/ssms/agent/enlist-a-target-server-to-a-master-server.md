---
title: Inscrever um servidor de destino em um servidor mestre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- enlisting target servers [SQL Server]
- SQL Server Agent jobs, target servers
- master servers [SQL Server], enlisting target servers
- SQL Server Agent jobs, master servers
- target servers [SQL Server], enlisting
ms.assetid: 7633adb5-d140-4e58-a8f2-5b4b50c2f95b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 256f1a78d298d89a36412ee5689695f3ab3fde8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569021"
---
# <a name="enlist-a-target-server-to-a-master-server"></a><span data-ttu-id="a41b3-102">Inscrever um servidor de destino em um servidor mestre</span><span class="sxs-lookup"><span data-stu-id="a41b3-102">Enlist a Target Server to a Master Server</span></span>
  <span data-ttu-id="a41b3-103">Este tópico descreve como adicionar servidores de destino a uma configuração de administração multisservidor.</span><span class="sxs-lookup"><span data-stu-id="a41b3-103">This topic describes how to add target servers to a multiserver administration configuration.</span></span> <span data-ttu-id="a41b3-104">Execute este procedimento a partir do servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="a41b3-104">Run this procedure from the master server.</span></span> <span data-ttu-id="a41b3-105">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../includes/tsql-md.md)]ou o SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="a41b3-105">in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="a41b3-106">Para obter informações sobre como a conta do Windows usada para o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent afeta um ambiente multisservidor, consulte [Criar um ambiente multisservidor](create-a-multiserver-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a41b3-106">For information about how the Windows account used for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service affects a multiserver environment, see [Create a Multiserver Environment](create-a-multiserver-environment.md).</span></span>  
  
 <span data-ttu-id="a41b3-107">Criptografia SSL completa e validação de certificado encontram-se habilitadas, por padrão, para conexões entre servidores mestre e servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="a41b3-107">Full Secure Sockets Layer (SSL) encryption and certificate validation is enabled for connections between master servers and target servers by default.</span></span> <span data-ttu-id="a41b3-108">Para obter mais informações, veja [Definir opções de criptografia em servidores de destino](set-encryption-options-on-target-servers.md).</span><span class="sxs-lookup"><span data-stu-id="a41b3-108">For more information, see [Set Encryption Options on Target Servers](set-encryption-options-on-target-servers.md).</span></span>  
  
 <span data-ttu-id="a41b3-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="a41b3-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a41b3-110">**Para inscrever um servidor de destino, usando:**</span><span class="sxs-lookup"><span data-stu-id="a41b3-110">**To enlist a target server, using:**</span></span>  
  
     [<span data-ttu-id="a41b3-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a41b3-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a41b3-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a41b3-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a41b3-113">SMO</span><span class="sxs-lookup"><span data-stu-id="a41b3-113">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a41b3-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a41b3-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="a41b3-115">Para inscrever um servidor de destino</span><span class="sxs-lookup"><span data-stu-id="a41b3-115">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="a41b3-116">No **Pesquisador de Objetos**, expanda um servidor que esteja configurado como servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="a41b3-116">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="a41b3-117">Clique com o botão direito do mouse em **SQL Server Agent**, aponte para **Administração Multisservidor**e clique em **Adicionar Servidores de Destino**.</span><span class="sxs-lookup"><span data-stu-id="a41b3-117">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Add Target Servers**.</span></span>  
  
3.  <span data-ttu-id="a41b3-118">Complete o Assistente de Servidor de Destino, que o guia nesse processo.</span><span class="sxs-lookup"><span data-stu-id="a41b3-118">Complete the Target Server Wizard, which guides you through the process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a41b3-119">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a41b3-119">Using Transact-SQL</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="a41b3-120">Para inscrever um servidor de destino</span><span class="sxs-lookup"><span data-stu-id="a41b3-120">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="a41b3-121">Use o procedimento armazenado `sp_msx_enlist`.</span><span class="sxs-lookup"><span data-stu-id="a41b3-121">Use the `sp_msx_enlist` stored procedure.</span></span>  <span data-ttu-id="a41b3-122">Para obter mais informações, consulte [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="a41b3-122">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="a41b3-123">Usando o SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="a41b3-123">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a41b3-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a41b3-124">See Also</span></span>  
 [<span data-ttu-id="a41b3-125">Administração automatizada em toda a empresa</span><span class="sxs-lookup"><span data-stu-id="a41b3-125">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
