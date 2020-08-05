---
title: Novo alias (guia alias) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 785eb6fb-f67e-449d-b1c8-c38dfbb95ef6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90742e5de3da0cac83c8b18eebba242ddb9a865d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573339"
---
# <a name="new-alias-alias-tab"></a><span data-ttu-id="c6cb6-102">Novo Alias (guia Alias)</span><span class="sxs-lookup"><span data-stu-id="c6cb6-102">New Alias (Alias Tab)</span></span>
  <span data-ttu-id="c6cb6-103">O alias é um nome alternativo que pode ser usado para fazer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-103">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="c6cb6-104">Ele encapsula os elementos necessários de uma cadeia de conexão, expondo-os com um nome escolhido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-104">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="c6cb6-105">Use a página **Alias** na caixa de diálogo **Alias - Novo** para especificar os elementos da cadeia de conexão de um alias.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-105">Use the **Alias** page on the **Alias - New** dialog box to specify the elements of the connection string for an alias.</span></span> <span data-ttu-id="c6cb6-106">Para alterar a cadeia de conexão de um alias existente, consulte [Propriedades &#60;Alias&#62; &#40;Guia Alias&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span><span class="sxs-lookup"><span data-stu-id="c6cb6-106">To change the connection string of an existing alias, see [&#60;Alias&#62; Properties &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span></span>  
  
 <span data-ttu-id="c6cb6-107">Os valores da grade **Propriedades** não precisam ser completados.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-107">All values in the **Properties** grid do not have to be completed.</span></span> <span data-ttu-id="c6cb6-108">As combinações válidas variam, dependendo do protocolo selecionado.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-108">Valid combinations vary depending on the protocol selected.</span></span> <span data-ttu-id="c6cb6-109">Consulte os tópicos listados abaixo para obter exemplos de combinações válidas.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-109">See the topics listed below for examples of valid combinations.</span></span>  
  
 <span data-ttu-id="c6cb6-110">**Nome do Alias**</span><span class="sxs-lookup"><span data-stu-id="c6cb6-110">**Alias Name**</span></span>  
 <span data-ttu-id="c6cb6-111">O nome (alias) que você deseja usar para se referir a essa conexão.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-111">The name (alias) that you want to use to refer to this connection.</span></span>  
  
 <span data-ttu-id="c6cb6-112">**Nome do Pipe** / **Número da Porta**</span><span class="sxs-lookup"><span data-stu-id="c6cb6-112">**Pipe Name** / **Port No**</span></span>  
 <span data-ttu-id="c6cb6-113">Elementos adicionais da cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-113">Additional elements of the connection string.</span></span> <span data-ttu-id="c6cb6-114">O nome desta caixa varia de acordo com o protocolo selecionado.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-114">The name of this box varies with the selected protocol.</span></span>  
  
 <span data-ttu-id="c6cb6-115">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="c6cb6-115">**Protocol**</span></span>  
 <span data-ttu-id="c6cb6-116">O protocolo usado para a conexão.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-116">The protocol used for the connection.</span></span>  
  
 <span data-ttu-id="c6cb6-117">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="c6cb6-117">**Server**</span></span>  
 <span data-ttu-id="c6cb6-118">O nome da instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo conectada.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-118">The name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance being connected to.</span></span>  
  
## <a name="when-to-use-an-alias"></a><span data-ttu-id="c6cb6-119">Quando usar um alias</span><span class="sxs-lookup"><span data-stu-id="c6cb6-119">When to Use an Alias</span></span>  
 <span data-ttu-id="c6cb6-120">Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se conecta a uma instância local do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o protocolo **Memória Compartilhada** , e se conecta a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em outro computador usando **TCP/IP** ou **Pipes Nomeados**.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-120">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connects to a local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **Shared Memory** protocol, and to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on another computer using either **TCP/IP** or **Named Pipes**.</span></span> <span data-ttu-id="c6cb6-121">Crie um alias quando estiver usando TCP/IP ou pipes nomeados e quiser fornecer uma cadeia de conexão personalizada, ou quando desejar usar um nome diferente do nome do servidor para a conexão.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-121">Create an alias when you are using TCP/IP or named pipes, and you want to provide a customized connection string, or when you want to use a name other than the server name for the connection.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="c6cb6-122">Exemplos</span><span class="sxs-lookup"><span data-stu-id="c6cb6-122">Examples</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c6cb6-123">não está escutando na porta TCP/IP padrão 1433, então você deseja fornecer uma cadeia de conexão com um número da porta diferente.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-123">is not listening on the default TCP/IP port of 1433 so you want to provide a connection string with a different port number.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c6cb6-124">não está escutando no pipe nomeado padrão, então você deseja fornecer uma cadeia de conexão com um nome de pipe diferente.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-124">is not listening on the default named pipe so you want to provide a connection string with a different pipe name.</span></span>  
  
-   <span data-ttu-id="c6cb6-125">Um aplicativo espera se conectar a um banco de dados no servidor `ACCT`, mas esse banco de dados foi consolidado como uma instância chamada `ACCT` em um servidor chamado `CENTRAL`.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-125">An application expects to connect to a database on the server named `ACCT`, but that database has been consolidated as an instance named `ACCT` on a server named `CENTRAL`.</span></span> <span data-ttu-id="c6cb6-126">O aplicativo não pode ser alterado facilmente.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-126">The application cannot easily be changed.</span></span> <span data-ttu-id="c6cb6-127">Crie um alias chamado `ACCT`, com uma cadeia de conexão que aponte para `CENTRAL\ACCT`.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-127">Create an alias named `ACCT`, with a connection string pointing to `CENTRAL\ACCT`.</span></span>  
  
## <a name="creating-a-valid-connection-string"></a><span data-ttu-id="c6cb6-128">Criando uma cadeia de conexão válida</span><span class="sxs-lookup"><span data-stu-id="c6cb6-128">Creating a Valid Connection String</span></span>  
 <span data-ttu-id="c6cb6-129">Consulte os seguintes tópicos para obter uma descrição e exemplos de combinações válidas de propriedades de alias:</span><span class="sxs-lookup"><span data-stu-id="c6cb6-129">See the following topics for a description and examples of valid combinations of alias properties:</span></span>  
  
-   [<span data-ttu-id="c6cb6-130">Criando uma cadeia de conexão válida usando o protocolo de memória compartilhada</span><span class="sxs-lookup"><span data-stu-id="c6cb6-130">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
-   [<span data-ttu-id="c6cb6-131">Criando uma cadeia de conexão válida usando TCP/IP</span><span class="sxs-lookup"><span data-stu-id="c6cb6-131">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
-   [<span data-ttu-id="c6cb6-132">Criando uma cadeia de conexão válida usando pipes nomeados</span><span class="sxs-lookup"><span data-stu-id="c6cb6-132">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
