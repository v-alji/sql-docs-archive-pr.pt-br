---
title: Configurar logs de erros do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.configureerrorlogs.f1
ms.assetid: 03f0d463-9b0b-4af9-a853-da936d75e5af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8acc27150f42049384e2789ef83ae66a737da9bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583837"
---
# <a name="configure-sql-server-error-logs"></a><span data-ttu-id="a8a54-102">Configurar logs de erros do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8a54-102">Configure SQL Server Error Logs</span></span>
  <span data-ttu-id="a8a54-103">Este tópico descreve como exibir ou modificar o modo como logs de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são reciclados.</span><span class="sxs-lookup"><span data-stu-id="a8a54-103">This topic describes how to view or modify the way [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs are recycled.</span></span>  
  
## <a name="to-open-the-configure-sql-server-error-logs-dialog-box"></a><span data-ttu-id="a8a54-104">Para abrir a caixa de diálogo Configurar Logs de Erros do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8a54-104">To open the Configure SQL Server Error Logs dialog box</span></span>  
  
1.  <span data-ttu-id="a8a54-105">No Pesquisador de Objetos, expanda a instância do SQL Server, expanda **Gerenciamento**, clique com o botão direito do mouse em **Logs do SQL Server**e clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="a8a54-105">In Object Explorer, expand the instance of SQL Server, expand **Management**, right-click **SQL Server Logs**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="a8a54-106">Na caixa de diálogo **Configurar Logs de Erros do SQL Server** , escolha uma das opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="a8a54-106">In the **Configure SQL Server Error Logs** dialog box, choose from the following options.</span></span>  
  
     <span data-ttu-id="a8a54-107">**Limite o número dos arquivos de log de erros antes que eles sejam reciclados**</span><span class="sxs-lookup"><span data-stu-id="a8a54-107">**Limit the number of the error log files before they are recycled**</span></span>  
     <span data-ttu-id="a8a54-108">Verifique e limite o número de logs de erros criados antes que eles sejam reciclados.</span><span class="sxs-lookup"><span data-stu-id="a8a54-108">Check to limit the number of error logs created before they are recycled.</span></span> <span data-ttu-id="a8a54-109">Um novo log de erros é criado a cada vez que uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é iniciada.</span><span class="sxs-lookup"><span data-stu-id="a8a54-109">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a8a54-110">retém backups dos seis últimos logs, a não ser que essa opção seja marcada um número máximo diferente de arquivos de log de erros seja especificado, logo abaixo.</span><span class="sxs-lookup"><span data-stu-id="a8a54-110">retains backups of the previous six logs, unless you check this option, and specify a different maximum number of error log files below.</span></span>  
  
     <span data-ttu-id="a8a54-111">**Número máximo de arquivos de log de erros**</span><span class="sxs-lookup"><span data-stu-id="a8a54-111">**Maximum number of error log files**</span></span>  
     <span data-ttu-id="a8a54-112">Especifique o número máximo de arquivos de log de erros criados, antes que eles sejam reciclados.</span><span class="sxs-lookup"><span data-stu-id="a8a54-112">Specify the maximum number of error log files created before they are recycled.</span></span> <span data-ttu-id="a8a54-113">O padrão é 6, que é o número de logs de backup anteriores que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , retém antes de reciclá-los.</span><span class="sxs-lookup"><span data-stu-id="a8a54-113">The default is 6, which is the number of previous backup logs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains before recycling them.</span></span>  
  
  
