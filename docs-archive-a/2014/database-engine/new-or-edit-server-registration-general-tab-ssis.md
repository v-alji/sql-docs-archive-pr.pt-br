---
title: Novo ou editar registro de servidor (guia geral) (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.dts.f1
ms.assetid: b586b736-344b-4e42-83ee-96f66ad433a5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4968c3f98b8bab5b2e641e6fb1e30a6d682f9b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582604"
---
# <a name="new-or-edit-server-registration-general-tab-ssis"></a><span data-ttu-id="66fd6-102">Novo registro ou editar registro de servidor (guia Geral) (SSIS)</span><span class="sxs-lookup"><span data-stu-id="66fd6-102">New or Edit Server Registration (General Tab) (SSIS)</span></span>
  <span data-ttu-id="66fd6-103">Use esta guia para especificar opções ao registrar [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66fd6-103">Use this tab to specify options when registering [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="66fd6-104">Para acessar essa página, em Servidores Registrados, clique em **Integration Services** na barra de ferramentas **Servidores Registrados** , clique com o botão direito do mouse em qualquer grupo de servidores registrados, aponte para **Novo**e clique em **Registro do Servidor**.</span><span class="sxs-lookup"><span data-stu-id="66fd6-104">To access this page, in Registered Servers, click **Integration Services** on the **Registered Servers** toolbar, right-click any registered servers group, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="66fd6-105">Opções</span><span class="sxs-lookup"><span data-stu-id="66fd6-105">Options</span></span>  
 <span data-ttu-id="66fd6-106">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="66fd6-106">**Server type**</span></span>  
 <span data-ttu-id="66fd6-107">Quando um servidor é registrado em Servidores Registrados, a caixa **Tipo de servidor** é somente leitura e corresponde ao tipo de servidor exibido em Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="66fd6-107">When a server is registered in Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in Registered Servers.</span></span> <span data-ttu-id="66fd6-108">Para registrar um tipo diferente de servidor, clique em **Mecanismo de Banco de Dados**, **Analysis Server**, **Reporting Services**, **SQL Server Compact** **Edition** ou **Integration Services** na barra de ferramentas **Servidores Registrados** antes de começar a registrar um novo servidor.</span><span class="sxs-lookup"><span data-stu-id="66fd6-108">To register a different type of server, click **Database Engine**, **Analysis Server**, **Reporting Services**, **SQL Server Compact** **Edition**, or **Integration Services** on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="66fd6-109">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="66fd6-109">**Server name**</span></span>  
 <span data-ttu-id="66fd6-110">Selecione o servidor ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="66fd6-110">Select the server to which to connect.</span></span> <span data-ttu-id="66fd6-111">O servidor conectado da última vez é exibido por padrão.</span><span class="sxs-lookup"><span data-stu-id="66fd6-111">The server last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="66fd6-112">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="66fd6-112">**Authentication**</span></span>  
 <span data-ttu-id="66fd6-113">O modo de Autenticação do Windows permite que um usuário se conecte por meio de uma conta de usuário do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="66fd6-113">Windows Authentication mode allows a user to connect through a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="66fd6-114">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="66fd6-114">**User name**</span></span>  
 <span data-ttu-id="66fd6-115">Essa opção não está disponível nesta versão.</span><span class="sxs-lookup"><span data-stu-id="66fd6-115">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="66fd6-116">**Senha**</span><span class="sxs-lookup"><span data-stu-id="66fd6-116">**Password**</span></span>  
 <span data-ttu-id="66fd6-117">Essa opção não está disponível nesta versão.</span><span class="sxs-lookup"><span data-stu-id="66fd6-117">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="66fd6-118">**Lembrar senha**</span><span class="sxs-lookup"><span data-stu-id="66fd6-118">**Remember password**</span></span>  
 <span data-ttu-id="66fd6-119">Essa opção não está disponível nesta versão.</span><span class="sxs-lookup"><span data-stu-id="66fd6-119">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="66fd6-120">**Nome do servidor registrado**</span><span class="sxs-lookup"><span data-stu-id="66fd6-120">**Registered server name**</span></span>  
 <span data-ttu-id="66fd6-121">O nome que você deseja exibir nos **servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="66fd6-121">The name you want to appear in **Registered Servers**.</span></span> <span data-ttu-id="66fd6-122">Esse nome não precisa corresponder à caixa **Nome do servidor** .</span><span class="sxs-lookup"><span data-stu-id="66fd6-122">This name does not have to match the **Server name** box.</span></span>  
  
 <span data-ttu-id="66fd6-123">**Descrição do servidor registrado**</span><span class="sxs-lookup"><span data-stu-id="66fd6-123">**Registered server description**</span></span>  
 <span data-ttu-id="66fd6-124">Digite uma descrição opcional do servidor.</span><span class="sxs-lookup"><span data-stu-id="66fd6-124">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="66fd6-125">**Test**</span><span class="sxs-lookup"><span data-stu-id="66fd6-125">**Test**</span></span>  
 <span data-ttu-id="66fd6-126">Clique para testar a conexão com o servidor selecionado em **Nome do servidor**.</span><span class="sxs-lookup"><span data-stu-id="66fd6-126">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="66fd6-127">**Salvar**</span><span class="sxs-lookup"><span data-stu-id="66fd6-127">**Save**</span></span>  
 <span data-ttu-id="66fd6-128">Clique para salvar as configurações de Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="66fd6-128">Click to save the Registered Servers settings.</span></span>  
  
  
