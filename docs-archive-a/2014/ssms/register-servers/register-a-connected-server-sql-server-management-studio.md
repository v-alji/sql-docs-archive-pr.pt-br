---
title: Registrar um servidor conectado
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.f1
helpviewer_keywords:
- Registered Servers [SQL Server], register connected servers
- connected server registrations [SQL Server]
ms.assetid: 77deb5f5-0f80-484f-8b8b-29afa67ec18f
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 1d337d2da7d305165307745fb02526e37b53bbd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572318"
---
# <a name="register-a-connected-server-sql-server-management-studio"></a><span data-ttu-id="54c3c-102">Registrar-se a um servidor conectado (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="54c3c-102">Register a Connected Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="54c3c-103">Este tópico descreve como registrar servidores no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54c3c-103">This topic describes how to register servers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="54c3c-104">Registrando o servidor, você pode salvar a informação de conexão para os servidores que você acessa frequentemente.</span><span class="sxs-lookup"><span data-stu-id="54c3c-104">By registering the server, you can save the connection information for servers that you access frequently.</span></span> <span data-ttu-id="54c3c-105">Um servidor pode ser registrado antes de ser conectado, ou na hora da conexão no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="54c3c-105">A server can be registered before connecting, or at the time of connection from Object Explorer.</span></span>  
  
 <span data-ttu-id="54c3c-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="54c3c-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="54c3c-107">**Para registrar um servidor, usando:**</span><span class="sxs-lookup"><span data-stu-id="54c3c-107">**To register a server, using:**</span></span>  
  
     [<span data-ttu-id="54c3c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54c3c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="54c3c-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54c3c-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-register-a-connected-server"></a><span data-ttu-id="54c3c-110">Para registrar um servidor conectado</span><span class="sxs-lookup"><span data-stu-id="54c3c-110">To register a connected server</span></span>  
  
1.  <span data-ttu-id="54c3c-111">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor ao qual você já está conectado e então clique em **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="54c3c-111">In Object Explorer, right-click a server to which you already are connected, and then click **Register**.</span></span>  
  
     <span data-ttu-id="54c3c-112">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="54c3c-112">**Server name**</span></span>  
     <span data-ttu-id="54c3c-113">Digite o nome que você deseja usar para o servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="54c3c-113">Enter the name you want to use for the registered server.</span></span> <span data-ttu-id="54c3c-114">Registrar um servidor local ou remoto usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] permite que você armazene as informações de conexão do servidor para conexões futuras.</span><span class="sxs-lookup"><span data-stu-id="54c3c-114">Registering a local or remote server using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] lets you store the server connection information for future connections.</span></span> <span data-ttu-id="54c3c-115">Esse campo define como padrão o nome do servidor digitado quando você se conectou ao servidor.</span><span class="sxs-lookup"><span data-stu-id="54c3c-115">This field defaults to the server name entered when you were connecting to the server.</span></span> <span data-ttu-id="54c3c-116">Você pode manter esse nome de servidor ou digitar outro nome de fácil uso para o servidor.</span><span class="sxs-lookup"><span data-stu-id="54c3c-116">You can retain this server name or enter another easy-to-use name for the server.</span></span>  
  
     <span data-ttu-id="54c3c-117">**Descrição do servidor**</span><span class="sxs-lookup"><span data-stu-id="54c3c-117">**Server description**</span></span>  
     <span data-ttu-id="54c3c-118">Digite uma descrição opcional do servidor.</span><span class="sxs-lookup"><span data-stu-id="54c3c-118">Enter an optional description of the server.</span></span> <span data-ttu-id="54c3c-119">O número máximo de caracteres permitido é 250.</span><span class="sxs-lookup"><span data-stu-id="54c3c-119">The maximum number of characters allowed is 250.</span></span>  
  
     <span data-ttu-id="54c3c-120">**Selecione um grupo de servidores**</span><span class="sxs-lookup"><span data-stu-id="54c3c-120">**Select a server group**</span></span>  
     <span data-ttu-id="54c3c-121">Selecione o grupo de servidores em que você deseja salvar o registro do servidor.</span><span class="sxs-lookup"><span data-stu-id="54c3c-121">Select the server group where you want to save the server registration.</span></span>  
  
     <span data-ttu-id="54c3c-122">**Novo Grupo**</span><span class="sxs-lookup"><span data-stu-id="54c3c-122">**New Group**</span></span>  
     <span data-ttu-id="54c3c-123">Clique para iniciar a caixa de diálogo **Novo Grupo** em que você pode criar um novo grupo de servidores para o servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="54c3c-123">Click to launch the **New Group** dialog box, where you can create a new server group for the registered server.</span></span>  
  
     <span data-ttu-id="54c3c-124">**Salvar**</span><span class="sxs-lookup"><span data-stu-id="54c3c-124">**Save**</span></span>  
     <span data-ttu-id="54c3c-125">Clique para salvar as informações que você digitou e criar um servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="54c3c-125">Click to save the information you have entered and create a registered server.</span></span>  
  
  
