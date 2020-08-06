---
title: Configurar auditoria de logon (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], logins
- logins [SQL Server], auditing
ms.assetid: 16961116-57ac-4eef-8037-791b26ade548
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7e05f6c254e098a67a5ce00435c009cd450af44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583296"
---
# <a name="configure-login-auditing-sql-server-management-studio"></a><span data-ttu-id="79db3-102">Configurar auditoria de logon (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="79db3-102">Configure Login Auditing (SQL Server Management Studio)</span></span>
  <span data-ttu-id="79db3-103">Este tópico descreve como configurar a auditoria de logon no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] para monitorar atividade de logon do [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79db3-103">This topic describes how to configure login auditing in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] to monitor [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] login activity.</span></span> <span data-ttu-id="79db3-104">A auditoria de logon pode ser configurada de modo a gravar registros no log de erros ao ocorrerem os eventos abaixo.</span><span class="sxs-lookup"><span data-stu-id="79db3-104">Login auditing can be configured to write to the error log on the following events.</span></span>  
  
-   <span data-ttu-id="79db3-105">Logons com falha</span><span class="sxs-lookup"><span data-stu-id="79db3-105">Failed logins</span></span>  
  
-   <span data-ttu-id="79db3-106">Logons com êxito</span><span class="sxs-lookup"><span data-stu-id="79db3-106">Successful logins</span></span>  
  
-   <span data-ttu-id="79db3-107">Logons com falha e bem sucedidos</span><span class="sxs-lookup"><span data-stu-id="79db3-107">Both failed and successful logins</span></span>  
  
 <span data-ttu-id="79db3-108">Você deve reinicializar o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para que esta opção entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="79db3-108">You must restart [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before this option will take effect.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="79db3-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="79db3-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-login-auditing"></a><span data-ttu-id="79db3-110">Para configurar a auditoria de logon</span><span class="sxs-lookup"><span data-stu-id="79db3-110">To configure login auditing</span></span>  
  
1.  <span data-ttu-id="79db3-111">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] com o Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="79db3-111">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="79db3-112">No Pesquisador de Objetos, clique com o botão direito do mouse no nome do servidor e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="79db3-112">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="79db3-113">Na página **Segurança** , em auditoria de **Logon** , clique na opção desejada e feche a página **Propriedades do Servidor** .</span><span class="sxs-lookup"><span data-stu-id="79db3-113">On the **Security** page, under **Login** auditing, click the desired option and close the **Server Properties** page.</span></span>  
  
4.  <span data-ttu-id="79db3-114">No Pesquisador de Objetos, clique com o botão direito do mouse no nome do servidor e clique em **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="79db3-114">In Object Explorer, right-click the server name, and then click **Restart**.</span></span>  
  
  
