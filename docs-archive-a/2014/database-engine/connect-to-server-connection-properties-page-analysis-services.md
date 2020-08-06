---
title: Conectar ao servidor (página Propriedades da Conexão) Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoas.connectionproperties.f1
ms.assetid: 26cf53e3-3bcb-4697-8a88-53e93bc68b56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 04706671ea8b0a50f2bf72cd7b73db88dce34d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678285"
---
# <a name="connect-to-server-connection-properties-page-analysis-services"></a><span data-ttu-id="18b7b-102">Conectar ao servidor (página Propriedades da Conexão) Analysis Services</span><span class="sxs-lookup"><span data-stu-id="18b7b-102">Connect to Server (Connection Properties Page) Analysis Services</span></span>
  <span data-ttu-id="18b7b-103">Use essa guia para exibir ou especificar opções ao se conectar [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou registrar [!INCLUDE[ssAS](../includes/ssas-md.md)] em **servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="18b7b-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] or registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="18b7b-104">**Conectar** e **Opções** são exibidas apenas nessa caixa de diálogo durante a conexão.</span><span class="sxs-lookup"><span data-stu-id="18b7b-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="18b7b-105">**Testar** e **Salvar** só aparecem nesta caixa de diálogo durante o registro no [!INCLUDE[ssAS](../includes/ssas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18b7b-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssAS](../includes/ssas-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="18b7b-106">Opções</span><span class="sxs-lookup"><span data-stu-id="18b7b-106">Options</span></span>  
 <span data-ttu-id="18b7b-107">**Conectar ao banco de dados**</span><span class="sxs-lookup"><span data-stu-id="18b7b-107">**Connect to database**</span></span>  
 <span data-ttu-id="18b7b-108">Selecione um banco de dados com o qual deseja se conectar na lista.</span><span class="sxs-lookup"><span data-stu-id="18b7b-108">Select a database to connect to from the list.</span></span> <span data-ttu-id="18b7b-109">Se você selecionar **\<default>** , você será conectado ao banco de dados padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="18b7b-109">If you select **\<default>**, you will be connected to the default database for the server.</span></span> <span data-ttu-id="18b7b-110">Se você selecionar **\<Browse server>** , poderá procurar no servidor o banco de dados ao qual deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="18b7b-110">If you select **\<Browse server>**, you can browse the server for the database you would like to connect to.</span></span>  
  
 <span data-ttu-id="18b7b-111">**Tempo limite da conexão**</span><span class="sxs-lookup"><span data-stu-id="18b7b-111">**Connection timeout**</span></span>  
 <span data-ttu-id="18b7b-112">Insira o número de segundos de espera para que uma conexão seja estabelecida antes de atingir o tempo limite. O valor padrão é 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="18b7b-112">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="18b7b-113">**Tempo limite de execução**</span><span class="sxs-lookup"><span data-stu-id="18b7b-113">**Execution timeout**</span></span>  
 <span data-ttu-id="18b7b-114">Digite o tempo em segundos que se deve esperar antes que a execução de uma tarefa seja concluída no servidor.</span><span class="sxs-lookup"><span data-stu-id="18b7b-114">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="18b7b-115">O valor padrão é zero segundo, o que indica que não há nenhum tempo limite.</span><span class="sxs-lookup"><span data-stu-id="18b7b-115">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="18b7b-116">**Criptografar a conexão**</span><span class="sxs-lookup"><span data-stu-id="18b7b-116">**Encrypt connection**</span></span>  
 <span data-ttu-id="18b7b-117">Força a criptografia da conexão.</span><span class="sxs-lookup"><span data-stu-id="18b7b-117">Forces encryption of the connection.</span></span>  
  
 <span data-ttu-id="18b7b-118">**Redefinir Tudo**</span><span class="sxs-lookup"><span data-stu-id="18b7b-118">**Reset All**</span></span>  
 <span data-ttu-id="18b7b-119">Substitua todos os valores de propriedade de conexão digitados manualmente pelos valores padrão.</span><span class="sxs-lookup"><span data-stu-id="18b7b-119">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="18b7b-120">**Connect**</span><span class="sxs-lookup"><span data-stu-id="18b7b-120">**Connect**</span></span>  
 <span data-ttu-id="18b7b-121">Tenta estabelecer uma conexão usando os valores listados.</span><span class="sxs-lookup"><span data-stu-id="18b7b-121">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="18b7b-122">**Opções**</span><span class="sxs-lookup"><span data-stu-id="18b7b-122">**Options**</span></span>  
 <span data-ttu-id="18b7b-123">Clique para alterar a caixa de diálogo e ocultar as opções de conexão de servidor adicionais, como lembrar a senha.</span><span class="sxs-lookup"><span data-stu-id="18b7b-123">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="18b7b-124">**Test**</span><span class="sxs-lookup"><span data-stu-id="18b7b-124">**Test**</span></span>  
 <span data-ttu-id="18b7b-125">Ao registrar o [!INCLUDE[ssAS](../includes/ssas-md.md)] em **Servidores Registrados**, clique para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="18b7b-125">When registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="18b7b-126">**Salvar**</span><span class="sxs-lookup"><span data-stu-id="18b7b-126">**Save**</span></span>  
 <span data-ttu-id="18b7b-127">Salve as configurações em **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="18b7b-127">Saves the settings in **Registered Servers**.</span></span>  
  
  
