---
title: Exibir o log de aplicativos do Windows (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- application logs [SQL Server]
- logs [SQL Server], application
- monitoring Windows NT application log [SQL Server]
- Windows NT application logs [SQL Server]
- displaying logs
- monitoring [SQL Server], events
- logs [SQL Server], viewing
ms.assetid: 168a6c6e-12df-46a9-9904-55d63ca8fe14
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1255e95833d9fc56abd1700f5acb0d2f49ebf77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680390"
---
# <a name="view-the-windows-application-log-windows"></a><span data-ttu-id="f4798-102">Exibir o log de aplicativos do Windows (Windows)</span><span class="sxs-lookup"><span data-stu-id="f4798-102">View the Windows Application Log (Windows)</span></span>
  <span data-ttu-id="f4798-103">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é configurado para usar o log de aplicativos do Windows, cada sessão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] grava novos eventos nesse log.</span><span class="sxs-lookup"><span data-stu-id="f4798-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="f4798-104">Ao contrário do log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , não é criado um novo log de aplicativos cada vez que uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]é iniciada.</span><span class="sxs-lookup"><span data-stu-id="f4798-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-the-windows-application-log"></a><span data-ttu-id="f4798-105">Para exibir o log de aplicativos do Windows</span><span class="sxs-lookup"><span data-stu-id="f4798-105">To view the Windows application log</span></span>  
  
1.  <span data-ttu-id="f4798-106">No menu **Iniciar** , aponte para **Todos os Programas**, **Ferramentas Administrativas**e clique em **Visualizador de Eventos**.</span><span class="sxs-lookup"><span data-stu-id="f4798-106">On the **Start** menu, point to **All Programs**, point to **Administrative Tools**, and then click **Event Viewer**.</span></span>  
  
2.  <span data-ttu-id="f4798-107">No Visualizador de Eventos, clique em **Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="f4798-107">In Event Viewer, click **Application**.</span></span>  
  
3.  <span data-ttu-id="f4798-108">Os eventos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são identificados pela entrada **MSSQLSERVER** (as instâncias nomeadas são identificadas com **MSSQL$** _<instance_name>_ ) na coluna **Origem**.</span><span class="sxs-lookup"><span data-stu-id="f4798-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events are identified by the entry **MSSQLSERVER** (named instances are identified with **MSSQL$**_<instance_name>_) in the **Source** column.</span></span> <span data-ttu-id="f4798-109">Os eventos do SQL Server Agent são identificados pela entrada SQLSERVERAGENT (no caso de instâncias nomeadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], os eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent são identificados com **SQLAgent$** \<*instance_name*>).</span><span class="sxs-lookup"><span data-stu-id="f4798-109">SQL Server Agent events are identified by the entry SQLSERVERAGENT (for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events are identified with **SQLAgent$**\<*instance_name*>).</span></span> <span data-ttu-id="f4798-110">Os eventos do serviço do Microsoft Search são identificados pela entrada **Microsoft Search**.</span><span class="sxs-lookup"><span data-stu-id="f4798-110">Microsoft Search service events are identified by the entry **Microsoft Search**.</span></span>  
  
4.  <span data-ttu-id="f4798-111">Para exibir o log de um computador diferente, clique com o botão direito do mouse em **Visualizador de Eventos**, clique em **Conectar-se a outro computador** e preencha a caixa de diálogo **Selecionar Computador**.</span><span class="sxs-lookup"><span data-stu-id="f4798-111">To view the log of a different computer, right-click **Event Viewer**, click **Connect to another computer,** and complete the **Select Computer**dialog box.</span></span>  
  
5.  <span data-ttu-id="f4798-112">Opcionalmente, para exibir apenas eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no menu **Exibir** clique em **Filtro**e, na lista **Origem do evento** , selecione **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="f4798-112">Optionally, to display only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, on the **View** menu click **Filter**, and in the **Event source** list, select **MSSQLSERVER**.</span></span> <span data-ttu-id="f4798-113">Para exibir apenas eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, selecione **SQLSERVERAGENT** na lista **Origem do evento** .</span><span class="sxs-lookup"><span data-stu-id="f4798-113">To view only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events, instead select **SQLSERVERAGENT** in the **Event source** list.</span></span>  
  
6.  <span data-ttu-id="f4798-114">Para exibir mais informações sobre um evento, clique duas vezes no evento.</span><span class="sxs-lookup"><span data-stu-id="f4798-114">To view more information about an event, double-click the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4798-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4798-115">See Also</span></span>  
 [<span data-ttu-id="f4798-116">Exibir o log de erros do SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f4798-116">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
