---
title: Conectar ao Servidor (página Logon) Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodtsserver.login.f1
- sql12.swb.connecttodts.login.f1
ms.assetid: 402c2de4-f4ea-40b0-909f-3ddf3bd59950
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 285518f4a1f3d9180d2c3c07a41bf75a00ea3593
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684875"
---
# <a name="connect-to-server-login-page-integration-services"></a><span data-ttu-id="4c22a-102">Conectar-se ao Servidor (página Logon) Integration Services</span><span class="sxs-lookup"><span data-stu-id="4c22a-102">Connect to Server (Login Page) Integration Services</span></span>
  <span data-ttu-id="4c22a-103">Use essa guia para exibir ou especificar as opções a seguir ao se conectar ao [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c22a-103">Use this tab to view or specify the following options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="4c22a-104">Opções</span><span class="sxs-lookup"><span data-stu-id="4c22a-104">Options</span></span>  
 <span data-ttu-id="4c22a-105">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="4c22a-105">**Server type**</span></span>  
 <span data-ttu-id="4c22a-106">Ao registrar um servidor a partir do Pesquisador de Objetos, selecione o tipo de servidor ao qual se conectar: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services.</span><span class="sxs-lookup"><span data-stu-id="4c22a-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="4c22a-107">O restante da caixa de diálogo mostra somente as opções que válidas ao tipo de servidor selecionado.</span><span class="sxs-lookup"><span data-stu-id="4c22a-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="4c22a-108">Ao registrar um servidor de Servidores Registrados, a caixa **Tipo de servidor** é somente leitura e corresponde ao tipo de servidor exibido no componente Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="4c22a-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="4c22a-109">Para registrar outro tipo de servidor, selecione [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services na barra de ferramentas Servidores Registrados antes de iniciar o registro de um novo servidor.</span><span class="sxs-lookup"><span data-stu-id="4c22a-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="4c22a-110">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="4c22a-110">**Server name**</span></span>  
 <span data-ttu-id="4c22a-111">Selecione o servidor ao qual conectar-se.</span><span class="sxs-lookup"><span data-stu-id="4c22a-111">Select the server to connect to.</span></span> <span data-ttu-id="4c22a-112">Por padrão, é exibida a instância de servidor usada na última conexão.</span><span class="sxs-lookup"><span data-stu-id="4c22a-112">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c22a-113">Não use *\<servername>* \\ *\<instancename>* , porque [!INCLUDE[ssIS](../includes/ssis-md.md)] o não oferece suporte a várias instâncias em um computador.</span><span class="sxs-lookup"><span data-stu-id="4c22a-113">Do not use *\<servername>*\\*\<instancename>*, because [!INCLUDE[ssIS](../includes/ssis-md.md)] does not support multiple instances on a computer.</span></span>  
  
 <span data-ttu-id="4c22a-114">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="4c22a-114">**Authentication**</span></span>  
 <span data-ttu-id="4c22a-115">Somente a Autenticação do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows está disponível para o [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c22a-115">Only [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span> <span data-ttu-id="4c22a-116">Windows permite que um usuário conecte-se por meio de uma conta de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="4c22a-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="4c22a-117">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="4c22a-117">**User name**</span></span>  
 <span data-ttu-id="4c22a-118">Essa opção não está disponível porque só a Autenticação do Windows está disponível para o [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c22a-118">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="4c22a-119">**Senha**</span><span class="sxs-lookup"><span data-stu-id="4c22a-119">**Password**</span></span>  
 <span data-ttu-id="4c22a-120">Essa opção não está disponível porque só a Autenticação do Windows está disponível para o [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c22a-120">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="4c22a-121">**Lembrar senha**</span><span class="sxs-lookup"><span data-stu-id="4c22a-121">**Remember password**</span></span>  
 <span data-ttu-id="4c22a-122">Essa opção não está disponível porque só a Autenticação do Windows está disponível para o [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c22a-122">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="4c22a-123">**Connect**</span><span class="sxs-lookup"><span data-stu-id="4c22a-123">**Connect**</span></span>  
 <span data-ttu-id="4c22a-124">Conecte-se com o servidor selecionado acima.</span><span class="sxs-lookup"><span data-stu-id="4c22a-124">Connect to the server selected above.</span></span>  
  
 <span data-ttu-id="4c22a-125">**Opções**</span><span class="sxs-lookup"><span data-stu-id="4c22a-125">**Options**</span></span>  
 <span data-ttu-id="4c22a-126">Clique para alterar a caixa de diálogo e ocultar as opções de conexão de servidor adicionais, como lembrar a senha.</span><span class="sxs-lookup"><span data-stu-id="4c22a-126">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
  
