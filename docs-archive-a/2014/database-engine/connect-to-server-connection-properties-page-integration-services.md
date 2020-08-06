---
title: Conectar ao servidor (página Propriedades da conexão) Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodts.connectionproperties.f1
- sql12.ssiseditserverregistration.connectionproperties.f1
ms.assetid: c2513dab-8415-4e0c-9475-6d4ab97fea7c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 05f3d370a3f3a299bb90df53538b3fa3e90e28c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684879"
---
# <a name="connect-to-server-connection-properties-page-integration-services"></a><span data-ttu-id="5a330-102">Conectar ao Servidor (página Propriedades da Conexão) Integration Services</span><span class="sxs-lookup"><span data-stu-id="5a330-102">Connect to Server (Connection Properties Page) Integration Services</span></span>
  <span data-ttu-id="5a330-103">Use essa guia para exibir ou especificar opções ao se conectar [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou registrar [!INCLUDE[ssIS](../includes/ssis-md.md)] em **servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="5a330-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] or registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="5a330-104">**Conectar** e **Opções** são exibidas apenas nessa caixa de diálogo durante a conexão.</span><span class="sxs-lookup"><span data-stu-id="5a330-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="5a330-105">**Testar** e **Salvar** só aparecem nesta caixa de diálogo durante o registro no [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a330-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="5a330-106">Opções</span><span class="sxs-lookup"><span data-stu-id="5a330-106">Options</span></span>  
 <span data-ttu-id="5a330-107">**Número da porta**</span><span class="sxs-lookup"><span data-stu-id="5a330-107">**Port number**</span></span>  
 <span data-ttu-id="5a330-108">Insira o número da porta usada pelo [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a330-108">Enter the port number used by [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="5a330-109">**Tempo limite da conexão**</span><span class="sxs-lookup"><span data-stu-id="5a330-109">**Connection time-out**</span></span>  
 <span data-ttu-id="5a330-110">Insira o número de segundos de espera para que uma conexão seja estabelecida antes de atingir o tempo limite. O valor padrão é 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="5a330-110">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="5a330-111">**Tempo limite de execução**</span><span class="sxs-lookup"><span data-stu-id="5a330-111">**Execution time-out**</span></span>  
 <span data-ttu-id="5a330-112">Digite o tempo em segundos que se deve esperar antes que a execução de uma tarefa seja concluída no servidor.</span><span class="sxs-lookup"><span data-stu-id="5a330-112">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="5a330-113">O valor padrão é zero segundo, o que indica que não há nenhum tempo limite.</span><span class="sxs-lookup"><span data-stu-id="5a330-113">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="5a330-114">**Redefinir Tudo**</span><span class="sxs-lookup"><span data-stu-id="5a330-114">**Reset All**</span></span>  
 <span data-ttu-id="5a330-115">Substitua todos os valores de propriedade de conexão digitados manualmente pelos valores padrão.</span><span class="sxs-lookup"><span data-stu-id="5a330-115">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="5a330-116">**Connect**</span><span class="sxs-lookup"><span data-stu-id="5a330-116">**Connect**</span></span>  
 <span data-ttu-id="5a330-117">Tenta estabelecer uma conexão usando os valores listados.</span><span class="sxs-lookup"><span data-stu-id="5a330-117">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="5a330-118">**Opções**</span><span class="sxs-lookup"><span data-stu-id="5a330-118">**Options**</span></span>  
 <span data-ttu-id="5a330-119">Clique para alterar a caixa de diálogo e ocultar as opções de conexão de servidor adicionais, como lembrar a senha.</span><span class="sxs-lookup"><span data-stu-id="5a330-119">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="5a330-120">**Test**</span><span class="sxs-lookup"><span data-stu-id="5a330-120">**Test**</span></span>  
 <span data-ttu-id="5a330-121">Ao registrar o [!INCLUDE[ssIS](../includes/ssis-md.md)] em **Servidores Registrados**, clique para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="5a330-121">When registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="5a330-122">**Salvar**</span><span class="sxs-lookup"><span data-stu-id="5a330-122">**Save**</span></span>  
 <span data-ttu-id="5a330-123">Salve as configurações em **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="5a330-123">Saves the settings in **Registered Servers**.</span></span>  
  
  
