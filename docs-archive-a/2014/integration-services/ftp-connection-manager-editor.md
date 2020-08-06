---
title: Editor do Gerenciador de conexões de FTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftpconnectionmanager.f1
helpviewer_keywords:
- FTP Connection Manager Editor
ms.assetid: 874b6585-255b-4a43-8396-bb08c3e8ac2b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d14635a4d90c267801f6d372dda5c7bcc7f4869f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686329"
---
# <a name="ftp-connection-manager-editor"></a><span data-ttu-id="5c394-102">Editor do Gerenciador de Conexões FTP</span><span class="sxs-lookup"><span data-stu-id="5c394-102">FTP Connection Manager Editor</span></span>
  <span data-ttu-id="5c394-103">Use a caixa de diálogo **Editor do Gerenciador de Conexões FTP** para especificar as propriedades de conexão com um servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="5c394-103">Use the **FTP Connection Manager Editor** dialog box to specify properties for connecting to an FTP server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5c394-104">O gerenciador de conexões de FTP dá suporte apenas para autenticação anônima e autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="5c394-104">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="5c394-105">Ele não suporta a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="5c394-105">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="5c394-106">Para saber mais sobre o gerenciador de conexões FTP, consulte [Gerenciador de Conexões FTP](connection-manager/ftp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5c394-106">To learn more about the FTP connection manager, see [FTP Connection Manager](connection-manager/ftp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5c394-107">Opções</span><span class="sxs-lookup"><span data-stu-id="5c394-107">Options</span></span>  
 <span data-ttu-id="5c394-108">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="5c394-108">**Server name**</span></span>  
 <span data-ttu-id="5c394-109">Forneça o nome do servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="5c394-109">Provide the name of the FTP server.</span></span>  
  
 <span data-ttu-id="5c394-110">**Porta do servidor**</span><span class="sxs-lookup"><span data-stu-id="5c394-110">**Server port**</span></span>  
 <span data-ttu-id="5c394-111">Especifique o número da porta no servidor FTP a ser usada na conexão.</span><span class="sxs-lookup"><span data-stu-id="5c394-111">Specify the port number on the FTP server to use for the connection.</span></span> <span data-ttu-id="5c394-112">O valor padrão dessa propriedade é **21**.</span><span class="sxs-lookup"><span data-stu-id="5c394-112">The default value of this property is **21**.</span></span>  
  
 <span data-ttu-id="5c394-113">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="5c394-113">**User name**</span></span>  
 <span data-ttu-id="5c394-114">Forneça um nome de usuário para acessar o servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="5c394-114">Provide a user name to access the FTP server.</span></span> <span data-ttu-id="5c394-115">O valor padrão dessa propriedade é **anonymous**.</span><span class="sxs-lookup"><span data-stu-id="5c394-115">The default value of this property is **anonymous**.</span></span>  
  
 <span data-ttu-id="5c394-116">**Senha**</span><span class="sxs-lookup"><span data-stu-id="5c394-116">**Password**</span></span>  
 <span data-ttu-id="5c394-117">Forneça uma senha para acessar o servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="5c394-117">Provide the password to access the FTP server.</span></span>  
  
 <span data-ttu-id="5c394-118">**Tempo limite (em segundos)**</span><span class="sxs-lookup"><span data-stu-id="5c394-118">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="5c394-119">Especifique o número de segundos que a tarefa leva antes de atingir o tempo limite. Um valor de **0** indica uma quantidade infinita de tempo.</span><span class="sxs-lookup"><span data-stu-id="5c394-119">Specify the number of seconds the task takes before timing out. A value of **0** indicates an infinite amount of time.</span></span> <span data-ttu-id="5c394-120">O valor padrão dessa propriedade é **60**.</span><span class="sxs-lookup"><span data-stu-id="5c394-120">The default value of this property is **60**.</span></span>  
  
 <span data-ttu-id="5c394-121">**Usar modo passivo**</span><span class="sxs-lookup"><span data-stu-id="5c394-121">**Use passive mode**</span></span>  
 <span data-ttu-id="5c394-122">Especifique se o servidor ou o cliente inicia a conexão.</span><span class="sxs-lookup"><span data-stu-id="5c394-122">Specify whether the server or the client initiates the connection.</span></span> <span data-ttu-id="5c394-123">No modo ativo, o servidor inicia a conexão e, no modo passivo, o cliente ativa a conexão.</span><span class="sxs-lookup"><span data-stu-id="5c394-123">The server initiates the connection in active mode, and the client activates the connection in passive mode.</span></span> <span data-ttu-id="5c394-124">O valor padrão dessa propriedade é **active mode**.</span><span class="sxs-lookup"><span data-stu-id="5c394-124">The default value of this property is **active mode**.</span></span>  
  
 <span data-ttu-id="5c394-125">**Novas tentativas**</span><span class="sxs-lookup"><span data-stu-id="5c394-125">**Retries**</span></span>  
 <span data-ttu-id="5c394-126">Especifique o número de vezes que a tarefa tenta fazer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="5c394-126">Specify the number of times the task attempts to make a connection.</span></span> <span data-ttu-id="5c394-127">Um valor de **0** indica que não há limite ao número de tentativas.</span><span class="sxs-lookup"><span data-stu-id="5c394-127">A value of **0** indicates no limit to the number of attempts.</span></span>  
  
 <span data-ttu-id="5c394-128">**Tamanho da parte (em KB)**</span><span class="sxs-lookup"><span data-stu-id="5c394-128">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="5c394-129">Forneça um tamanho de parte em kilobytes para transmissão de dados.</span><span class="sxs-lookup"><span data-stu-id="5c394-129">Provide a chunk size in kilobytes for transmitting data.</span></span>  
  
 <span data-ttu-id="5c394-130">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="5c394-130">**Test Connection**</span></span>  
 <span data-ttu-id="5c394-131">Depois de configurar o Gerenciador de Conexões FTP, confirme se a conexão é viável clicando em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="5c394-131">After configuring the FTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c394-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5c394-132">See Also</span></span>  
 [<span data-ttu-id="5c394-133">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="5c394-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
