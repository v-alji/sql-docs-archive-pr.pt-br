---
title: Ocultar objetos do sistema no Pesquisador de Objetos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- hiding system objects
- system objects [SQL Server]
- objects [SQL Server], hiding
- Object Explorer, hiding objects
ms.assetid: c01d8804-838c-4f75-b78c-80e41e4fffdc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1e039446191154144dd6660fa6e8d3b4b65d1013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568313"
---
# <a name="hide-system-objects-in-object-explorer"></a><span data-ttu-id="00a26-102">Ocultar objetos do sistema no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="00a26-102">Hide System Objects in Object Explorer</span></span>
  <span data-ttu-id="00a26-103">Este tópico descreve como ocultar objetos do sistema no Pesquisador de Objetos no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00a26-103">This topic describes how to hide system objects in Object Explorer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="00a26-104">O nó **Bancos de Dados** do Pesquisador de Objetos contém objetos do sistema, como os bancos de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="00a26-104">The **Databases** node of Object Explorer contains system objects such as the system databases.</span></span> <span data-ttu-id="00a26-105">Use as páginas **Ferramentas**/**Opções** para ocultar os objetos do sistema.</span><span class="sxs-lookup"><span data-stu-id="00a26-105">Use the **Tools**/**Options** pages to hide the system objects.</span></span> <span data-ttu-id="00a26-106">Alguns objetos do sistema, como funções de sistema e tipos de dados do sistema, não são afetados por essa configuração.</span><span class="sxs-lookup"><span data-stu-id="00a26-106">Some system objects, such as system functions and system data types, are not affected by this setting.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="00a26-107">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="00a26-107">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-hide-system-objects-in-object-explorer"></a><span data-ttu-id="00a26-108">Para ocultar objetos do sistema no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="00a26-108">To hide system objects in Object Explorer</span></span>  
  
1.  <span data-ttu-id="00a26-109">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="00a26-109">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="00a26-110">Na página **Ambiente/Inicialização** , selecione **Ocultar objetos do sistema no Pesquisador de Objetos**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="00a26-110">On the **Environment/Startup** page, select **Hide system objects in Object Explorer**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="00a26-111">Na caixa de diálogo **SQL Server Management Studio** , clique em **OK** para reconhecer que o SQL Server Management Studio deve ser reiniciado para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="00a26-111">In the **SQL Server Management Studio** dialog box, click **OK** to acknowledge that SQL Server Management Studio must be restarted for this change to take effect.</span></span>  
  
4.  <span data-ttu-id="00a26-112">Feche e reabra o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="00a26-112">Close and reopen SQL Server Management Studio.</span></span>  
  
  
