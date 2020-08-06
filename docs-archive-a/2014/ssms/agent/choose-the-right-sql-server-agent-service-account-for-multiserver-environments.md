---
title: Escolha a conta de serviço SQL Server Agent correta para ambientes multisservidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- multiserver environments [SQL Server], SQL Server Agent service account behavior
ms.assetid: a07e2f38-281c-495b-965b-13fad03ba548
author: stevestein
ms.author: sstein
ms.openlocfilehash: 94ef890f5d2ef2b85d2f4d1023a93747e903a7f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583328"
---
# <a name="choose-the-right-sql-server-agent-service-account-for-multiserver-environments"></a><span data-ttu-id="e0722-102">Escolher a conta de serviço do SQL Server Agent certa para ambientes multisservidor</span><span class="sxs-lookup"><span data-stu-id="e0722-102">Choose the Right SQL Server Agent Service Account for Multiserver Environments</span></span>
  <span data-ttu-id="e0722-103">A conta do Windows escolhida para o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pode afetar o comportamento de um ambiente multisservidor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e0722-103">The Windows account you choose for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can affect the behavior of a multiserver environment, as follows:</span></span>  
  
-   <span data-ttu-id="e0722-104">Se você executar o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sob uma conta que não seja membro do grupo Administradores do Windows local, a inscrição de servidores de destino em servidores mestre poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="e0722-104">If you run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service under an account that is not a member of the local Windows Administrators group, enlisting target servers to master servers may fail.</span></span> <span data-ttu-id="e0722-105">Se isso acontecer, a seguinte mensagem de erro será retornada:</span><span class="sxs-lookup"><span data-stu-id="e0722-105">If it does, the following error message is returned:</span></span>  
  
     <span data-ttu-id="e0722-106">"A operação de inscrição falhou".</span><span class="sxs-lookup"><span data-stu-id="e0722-106">"The enlistment operation failed."</span></span>  
  
     <span data-ttu-id="e0722-107">Reinicie os serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="e0722-107">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services to resolve this issue.</span></span>  
  
-   <span data-ttu-id="e0722-108">Quando o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é executado com a conta Sistema Local, só haverá suporte a operações de servidor mestre e servidor de destino se ambos residirem no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="e0722-108">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is run under the Local System account, master server-target server operations are supported only if both the master server and the target server reside on the same computer.</span></span> <span data-ttu-id="e0722-109">Se você usar essa configuração, a seguinte mensagem será retornada quando você inscrever servidores de destino para um servidor mestre:</span><span class="sxs-lookup"><span data-stu-id="e0722-109">If you use this configuration, the following message is returned when you enlist target servers to a master server:</span></span>  
  
     <span data-ttu-id="e0722-110">"Verifique se a conta de inicialização de agente de *<target_server_computer_name>* tem direitos para fazer logon como um servidor de destino".</span><span class="sxs-lookup"><span data-stu-id="e0722-110">"Ensure the agent start-up account for *<target_server_computer_name>* has rights to log on as targetServer."</span></span>  
  
     <span data-ttu-id="e0722-111">Você pode ignorar essa mensagem informativa.</span><span class="sxs-lookup"><span data-stu-id="e0722-111">You can ignore this informational message.</span></span> <span data-ttu-id="e0722-112">A operação de inscrição deve ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="e0722-112">The enlistment operation should complete successfully.</span></span>  
  
 <span data-ttu-id="e0722-113">Para obter mais informações sobre como escolher uma conta para o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, veja [Selecionar uma conta para o serviço do SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="e0722-113">For more information about choosing an account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span>  
  
  
