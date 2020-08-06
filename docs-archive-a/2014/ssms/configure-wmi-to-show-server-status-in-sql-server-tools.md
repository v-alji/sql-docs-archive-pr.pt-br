---
title: Configurar o WMI para mostrar o status do servidor nas ferramentas do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI Provider for Server Events, setting permissions
- WMI permissions [SQL Server]
ms.assetid: 7e97197b-ed4d-40d1-9a52-9ab1d92401d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 138abbe2b7b819d6afd6da62135f7cd7ce86496f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683894"
---
# <a name="configure-wmi-to-show-server-status-in-sql-server-tools"></a><span data-ttu-id="d6420-102">Configurar o WMI para mostrar o status do servidor nas ferramentas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6420-102">Configure WMI to Show Server Status in SQL Server Tools</span></span>
  <span data-ttu-id="d6420-103">Este tópico descreve como configurar o WMI para mostrar o status de servidor nas ferramentas do SQL Server no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6420-103">This topic describes how to configure WMI to show the server status in SQL Server tools in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d6420-104">Na conexão com servidores, os componentes Servidores Registrados e Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], assim como o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager, usam o Windows Management Instrumentation (WMI) para obter o status dos serviços do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) e do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="d6420-104">When connecting to servers, both the Registered Servers and Object Explorer components of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], as well as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager, use Windows Management Instrumentation (WMI) to obtain the status of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent (MSSQLSERVER) services.</span></span> <span data-ttu-id="d6420-105">Para exibir o status do serviço, o usuário deve ter direitos para acessar o objeto WMI remotamente.</span><span class="sxs-lookup"><span data-stu-id="d6420-105">To display the status of the service, the user must have rights to remotely access the WMI object.</span></span> <span data-ttu-id="d6420-106">O servidor deve ter o WMI instalado para que essa permissão possa ser configurada.</span><span class="sxs-lookup"><span data-stu-id="d6420-106">The server must have WMI installed to configure this permission.</span></span>  
  
##  <a name="to-configure-wmi-permission"></a><a name="SSMSProcedure"></a><span data-ttu-id="d6420-107">Para configurar a permissão WMI</span><span class="sxs-lookup"><span data-stu-id="d6420-107">To configure WMI permission</span></span>  
  
1.  <span data-ttu-id="d6420-108">No menu **Iniciar** no servidor remoto, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="d6420-108">On the **Start** menu on the remote server, click **Run**.</span></span>  
  
2.  <span data-ttu-id="d6420-109">Na caixa **abrir** , digite `wmimgmt.msc` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6420-109">In the **Open** box type `wmimgmt.msc`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d6420-110">No programa **Windows Management Infrastructure** , clique com o botão direito do mouse em **Controle WMI (Local)** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d6420-110">In the **Windows Management Infrastructure** program, right-click **WMI Control (Local)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="d6420-111">Na caixa de diálogo **Propriedades do Controle WMI (Local)** , na guia **Segurança** , expanda **Raiz**e clique em **CIMV2**.</span><span class="sxs-lookup"><span data-stu-id="d6420-111">In the **WMI Control (Local) Properties** dialog box, on the **Security** tab, expand **Root**, and then click **CIMV2**.</span></span>  
  
5.  <span data-ttu-id="d6420-112">Clique em **Segurança** para abrir a caixa de diálogo **Segurança de ROOT\CIMV2** .</span><span class="sxs-lookup"><span data-stu-id="d6420-112">Click **Security** to open the **Security for ROOT\CIMV2** dialog box.</span></span>  
  
6.  <span data-ttu-id="d6420-113">Adicione um grupo ou usuário à caixa **Nomes de grupo ou de usuário** e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="d6420-113">Add a group or user to the **Group or user names** box and select it.</span></span>  
  
7.  <span data-ttu-id="d6420-114">Na caixa **Permissões do** _\<group or user>_ , selecione a coluna **Permitir** da permissão **Habilitação Remota** para os usuários que desejam detectar remotamente o status do serviço.</span><span class="sxs-lookup"><span data-stu-id="d6420-114">In the **Permissions for**_\<group or user>_ box, select the **Allow** column, for the **Remote Enable** permission, for users whom you wish to remotely detect the service status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6420-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d6420-115">See Also</span></span>  
 [<span data-ttu-id="d6420-116">Iniciar, parar ou pausar o serviço do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="d6420-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
