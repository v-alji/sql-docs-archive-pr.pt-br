---
title: Conectar ao Servidor (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.analysisserver.f1
ms.assetid: 7e277d22-8d4b-422e-8882-7c5dd7a6d915
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b3530f38534e09ef19e77293880129274dfc211b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678287"
---
# <a name="connect-to-server-analysis-services"></a><span data-ttu-id="f8306-102">Conectar ao servidor (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f8306-102">Connect to Server (Analysis Services)</span></span>
  <span data-ttu-id="f8306-103">Use essa caixa de diálogo para exibir ou especificar opções ao se conectar ao [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8306-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="f8306-104">Opções</span><span class="sxs-lookup"><span data-stu-id="f8306-104">Options</span></span>  
 <span data-ttu-id="f8306-105">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="f8306-105">**Server type**</span></span>  
 <span data-ttu-id="f8306-106">Ao registrar um servidor a partir do Pesquisador de Objetos, selecione o tipo de servidor ao qual se conectar: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services.</span><span class="sxs-lookup"><span data-stu-id="f8306-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="f8306-107">O restante da caixa de diálogo mostra somente as opções que válidas ao tipo de servidor selecionado.</span><span class="sxs-lookup"><span data-stu-id="f8306-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="f8306-108">Ao registrar um servidor de Servidores Registrados, a caixa **Tipo de servidor** é somente leitura e corresponde ao tipo de servidor exibido no componente Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="f8306-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="f8306-109">Para registrar outro tipo de servidor, selecione [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services na barra de ferramentas Servidores Registrados antes de iniciar o registro de um novo servidor.</span><span class="sxs-lookup"><span data-stu-id="f8306-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="f8306-110">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="f8306-110">**Server name**</span></span>  
 <span data-ttu-id="f8306-111">Selecione a instância do servidor com a qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="f8306-111">Select the server instance to connect to.</span></span> <span data-ttu-id="f8306-112">Por padrão, é exibida a instância de servidor usada na última conexão.</span><span class="sxs-lookup"><span data-stu-id="f8306-112">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="f8306-113">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="f8306-113">**Authentication**</span></span>  
 <span data-ttu-id="f8306-114">Os modos de autenticação a seguir recebem suporte na conexão com uma instância do Analysis Services: Autenticação do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="f8306-114">The following authentication modes are supported when connecting to an instance of Analysis Services: [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="f8306-115">**Modo de Autenticação do Windows (Autenticação do Windows)**</span><span class="sxs-lookup"><span data-stu-id="f8306-115">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="f8306-116">O modo de **autenticação do Windows** permite que um usuário se conecte por meio de uma conta de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="f8306-116">**Windows Authentication** mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="f8306-117">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="f8306-117">**User name**</span></span>  
 <span data-ttu-id="f8306-118">Essa opção não está disponível nesta versão.</span><span class="sxs-lookup"><span data-stu-id="f8306-118">This option is not available in this release.</span></span> <span data-ttu-id="f8306-119">Digite o nome do usuário com o qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="f8306-119">Enter the user name to connect with.</span></span> <span data-ttu-id="f8306-120">Essa opção estará disponível somente se você decidiu conectar-se usando a **Autenticação do Windows**.</span><span class="sxs-lookup"><span data-stu-id="f8306-120">This option is only available if you have selected to connect using **Windows Authentication**.</span></span>  
  
 <span data-ttu-id="f8306-121">**Senha**</span><span class="sxs-lookup"><span data-stu-id="f8306-121">**Password**</span></span>  
 <span data-ttu-id="f8306-122">Essa opção não está disponível nesta versão.</span><span class="sxs-lookup"><span data-stu-id="f8306-122">This option is not available in this release.</span></span> <span data-ttu-id="f8306-123">Digite a senha do logon.</span><span class="sxs-lookup"><span data-stu-id="f8306-123">Enter the password for the login.</span></span> <span data-ttu-id="f8306-124">Essa opção poderá ser editada somente se você decidiu conectar-se usando a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8306-124">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="f8306-125">**Connect**</span><span class="sxs-lookup"><span data-stu-id="f8306-125">**Connect**</span></span>  
 <span data-ttu-id="f8306-126">Clique para conectar-se com o servidor selecionado acima.</span><span class="sxs-lookup"><span data-stu-id="f8306-126">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="f8306-127">**Opções**</span><span class="sxs-lookup"><span data-stu-id="f8306-127">**Options**</span></span>  
 <span data-ttu-id="f8306-128">Clique para exibir opções de conexão de servidor adicionais, como registrar um servidor e lembrar a senha.</span><span class="sxs-lookup"><span data-stu-id="f8306-128">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
