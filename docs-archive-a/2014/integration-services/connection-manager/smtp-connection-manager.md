---
title: Gerenciador de conexões SMTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMTP
- SMTP connection manager [Integration Services]
- connection managers [Integration Services], SMTP
ms.assetid: 3795d442-714b-4bbb-9acd-75bf277a468a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f3c090ab672790901baae01ae86f8d22e008b4ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685240"
---
# <a name="smtp-connection-manager"></a><span data-ttu-id="10875-102">Gerenciador de conexões SMTP</span><span class="sxs-lookup"><span data-stu-id="10875-102">SMTP Connection Manager</span></span>
  <span data-ttu-id="10875-103">Um gerenciador de conexões SMTP permite que um pacote conecte-se a um servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="10875-103">An SMTP connection manager enables a package to connect to a Simple Mail Transfer Protocol (SMTP) server.</span></span> <span data-ttu-id="10875-104">A tarefa Enviar Email incluída pelo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa um gerenciador de conexões SMTP.</span><span class="sxs-lookup"><span data-stu-id="10875-104">The Send Mail task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an SMTP connection manager.</span></span>  
  
 <span data-ttu-id="10875-105">Ao utilizar o Microsoft Exchange como servidor SMTP, você talvez precise configurar o gerenciador de conexões SMTP para utilizar a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="10875-105">When using Microsoft Exchange as the SMTP server, you may need to configure the SMTP connection manager to use Windows Authentication.</span></span> <span data-ttu-id="10875-106">Os servidores Exchange podem ser configurados para não permitir conexões SMTP não autenticadas.</span><span class="sxs-lookup"><span data-stu-id="10875-106">Exchange servers may be configured to not allow unauthenticated SMTP connections.</span></span>  
  
## <a name="configuration-the-smtp-connection-manager"></a><span data-ttu-id="10875-107">Configuração do gerenciador de conexões SMTP</span><span class="sxs-lookup"><span data-stu-id="10875-107">Configuration the SMTP Connection Manager</span></span>  
 <span data-ttu-id="10875-108">Quando você adiciona um gerenciador de conexões SMTP a um pacote, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] cria um gerenciador de conexões que será resolvido para uma conexão SMTP em tempo de execução, define as propriedades do gerenciador de conexões e adiciona o gerenciador de conexões à coleção `Connections` no pacote.</span><span class="sxs-lookup"><span data-stu-id="10875-108">When you add an SMTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="10875-109">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `SMTP`.</span><span class="sxs-lookup"><span data-stu-id="10875-109">The `ConnectionManagerType` property of the connection manager is set to `SMTP`.</span></span>  
  
 <span data-ttu-id="10875-110">Você pode configurar um gerenciador de conexões SMTP das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="10875-110">You can configure an SMTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="10875-111">Fornecendo uma sequência de conexão.</span><span class="sxs-lookup"><span data-stu-id="10875-111">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="10875-112">Especificando o nome de um servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="10875-112">Specify the name of an SMTP server.</span></span>  
  
-   <span data-ttu-id="10875-113">Especificando o método de autenticação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="10875-113">Specify the authentication method to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="10875-114">O gerenciador de conexões SMTP dá suporte apenas para autenticação anônima e Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="10875-114">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="10875-115">Ele não suporta a autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="10875-115">It does not support basic authentication.</span></span>  
  
-   <span data-ttu-id="10875-116">Especificando se é necessário criptografar a comunicação utilizando o SSL ao enviar mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="10875-116">Specify whether to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
 <span data-ttu-id="10875-117">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="10875-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="10875-118">Para obter mais informações sobre as propriedades que podem ser definidas no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Editor do Gerenciador de Conexões de SMTP](../smtp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="10875-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMTP Connection Manager Editor](../smtp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="10875-119">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="10875-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
