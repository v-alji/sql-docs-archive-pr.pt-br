---
title: Acessar o provedor WMI para gerenciamento de configuração usando WQL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
ms.assetid: 26499530-d93b-452b-bbe4-217ef1d11e68
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b58297c5e292ceb18a6e2e50e2b25b9aa352e2fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568369"
---
# <a name="access-wmi-provider-for-configuration-management-using-wql"></a><span data-ttu-id="3b592-102">Acessar o provedor WMI para o gerenciamento de configuração usando o WQL</span><span class="sxs-lookup"><span data-stu-id="3b592-102">Access WMI Provider for Configuration Management using WQL</span></span>
  <span data-ttu-id="3b592-103">Esta seção descreve como executar instruções de linguagem WQL da Instrumentação de Gerenciamento do Windows [!INCLUDE[msCoName](../../includes/msconame-md.md)] no Provedor de WMI para Gerenciamento do Computador.</span><span class="sxs-lookup"><span data-stu-id="3b592-103">This section describes how to execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Management Instrumentation Query Language (WQL) statements against the WMI Provider for Computer Management.</span></span>  
  
 <span data-ttu-id="3b592-104">O exemplo usa um editor de WQL, WBEMtest.exe, para executar consultas WQL no Provedor de WMI para enumerar serviços, protocolos de rede e aliases do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b592-104">The example uses a WQL editor, WBEMtest.exe, to run WQL queries against the WMI Provider to enumerate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network protocols, and aliases.</span></span>  
  
### <a name="querying-services-using-wbemtest"></a><span data-ttu-id="3b592-105">Consultando serviços que usam WBEMtest</span><span class="sxs-lookup"><span data-stu-id="3b592-105">Querying services using WBEMtest</span></span>  
  
1.  <span data-ttu-id="3b592-106">No menu **Iniciar** , clique em **executar**e, em seguida, digite `WBEMtest` .</span><span class="sxs-lookup"><span data-stu-id="3b592-106">From the **Start** menu, click **Run**, and then enter `WBEMtest`.</span></span>  
  
2.  <span data-ttu-id="3b592-107">A caixa de diálogo de WBEMtest.exe é exibida.</span><span class="sxs-lookup"><span data-stu-id="3b592-107">The WBEMtest.exe dialog appears.</span></span> <span data-ttu-id="3b592-108">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="3b592-108">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="3b592-109">No primeiro campo de texto, digite o namespace do Provedor de WMI para Gerenciamento do Computador: root\Microsoft\SqlServer\ComputerManagement11.</span><span class="sxs-lookup"><span data-stu-id="3b592-109">In the first text field, type the WMI Provider for Computer Management namespace: root\Microsoft\SqlServer\ComputerManagement11.</span></span> <span data-ttu-id="3b592-110">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="3b592-110">Click **Connect**.</span></span>  
  
4.  <span data-ttu-id="3b592-111">Clique em **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3b592-111">Click **Query**.</span></span> <span data-ttu-id="3b592-112">Digite uma consulta que retorne os serviços atuais em execução no computador local: **selecione \* em SqlService.**</span><span class="sxs-lookup"><span data-stu-id="3b592-112">Type a query that returns the current services running on the local computer: **SELECT \* FROM SqlService.**</span></span> <span data-ttu-id="3b592-113">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="3b592-113">Click **Apply**.</span></span>  
  
5.  <span data-ttu-id="3b592-114">Refine ainda mais a consulta, adicionando `WHERE ServiceName = "MSSQLSERVER"`.</span><span class="sxs-lookup"><span data-stu-id="3b592-114">Further refine the query by adding `WHERE ServiceName = "MSSQLSERVER"`.</span></span>  
  
  
