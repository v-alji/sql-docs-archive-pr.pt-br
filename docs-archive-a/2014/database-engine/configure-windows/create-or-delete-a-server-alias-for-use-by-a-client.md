---
title: Criar ou excluir um alias de servidor para uso por um cliente (SQL Server Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- server alias
helpviewer_keywords:
- aliases [SQL Server], deleting
- aliases [SQL Server], creating
ms.assetid: b687e376-ee33-470d-b65a-87246bfefe6f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bead257b40c33e3640b18890a7d109d774131123
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574908"
---
# <a name="create-or-delete-a-server-alias-for-use-by-a-client-sql-server-configuration-manager"></a><span data-ttu-id="f6c04-102">Criar ou excluir um alias de servidor para ser usado por um cliente (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="f6c04-102">Create or Delete a Server Alias for Use by a Client (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="f6c04-103">Este tópico descreve como criar ou excluir um alias de servidor no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6c04-103">This topic describes how to create or delete a server alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="f6c04-104">O alias é um nome alternativo que pode ser usado para fazer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="f6c04-104">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="f6c04-105">Ele encapsula os elementos necessários de uma cadeia de conexão, expondo-os com um nome escolhido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f6c04-105">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="f6c04-106">Aliases podem ser usados com qualquer aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="f6c04-106">Aliases can be used with any client application.</span></span> <span data-ttu-id="f6c04-107">Criando aliases de servidor, seu computador cliente pode se conectar a vários servidores usando protocolos de rede diferentes, sem a necessidade de especificar o protocolo e os detalhes da conexão para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="f6c04-107">By creating server aliases, your client computer can connect to multiple servers using different network protocols, without having to specify the protocol and connection details for each one.</span></span> <span data-ttu-id="f6c04-108">Além disso, você também poderá ter diferentes protocolos de rede habilitados o tempo todo, mesmo se precisar usá-los apenas ocasionalmente.</span><span class="sxs-lookup"><span data-stu-id="f6c04-108">In addition, you can also have different network protocols enabled all the time, even if you only need to use them occasionally.</span></span> <span data-ttu-id="f6c04-109">Se você configurou o servidor para escutar em um pipe nomeado ou número de porta que não seja padrão e desabilitou o serviço SQL Server Browser, crie um alias que especifique o novo pipe nomeado ou o número de porta.</span><span class="sxs-lookup"><span data-stu-id="f6c04-109">If you have configured the server to listen on a non-default port number or named pipe, and you have disabled the SQL Server Browser service, create an alias that specifies the new port number or named pipe.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f6c04-110">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6c04-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-create-an-alias"></a><span data-ttu-id="f6c04-111">Criar um alias</span><span class="sxs-lookup"><span data-stu-id="f6c04-111">To create an alias</span></span>  
  
1.  <span data-ttu-id="f6c04-112">No SQL Server Configuration Manager, expanda **Configuração do SQL Server Native Client**, clique com o botão direito do mouse em **Aliases**e clique em **Novo Alias**.</span><span class="sxs-lookup"><span data-stu-id="f6c04-112">In SQL Server Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Aliases**, and then click **New Alias**.</span></span>  
  
2.  <span data-ttu-id="f6c04-113">Na caixa **Nome do Alias** , digite o nome do alias.</span><span class="sxs-lookup"><span data-stu-id="f6c04-113">In the **Alias Name** box, type the name of the alias.</span></span> <span data-ttu-id="f6c04-114">Os aplicativos cliente usam este nome quando se conectam.</span><span class="sxs-lookup"><span data-stu-id="f6c04-114">Client applications use this name when they connect.</span></span>  
  
3.  <span data-ttu-id="f6c04-115">Na caixa **Servidor** , digite o nome ou o endereço IP de um servidor.</span><span class="sxs-lookup"><span data-stu-id="f6c04-115">In the **Server** box, type the name or IP address of a server.</span></span> <span data-ttu-id="f6c04-116">Para uma instância nomeada, acrescente o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="f6c04-116">For a named instance append the instance name.</span></span>  
  
4.  <span data-ttu-id="f6c04-117">Na caixa **Protocolo** , selecione o protocolo usado para este alias.</span><span class="sxs-lookup"><span data-stu-id="f6c04-117">In the **Protocol** box, select the protocol used for this alias.</span></span> <span data-ttu-id="f6c04-118">A seleção de um protocolo altera o título da caixa de propriedades opcional para Número da Porta, Nome do Pipe ou Cadeia de Conexão.</span><span class="sxs-lookup"><span data-stu-id="f6c04-118">Selecting a protocol, changes the title of the optional properties box to Port No, Pipe Name, or Connection String.</span></span>  
  
 <span data-ttu-id="f6c04-119">As cadeias de conexão descritas na Ajuda do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager podem ser úteis para programadores que criam suas próprias cadeias de conexão.</span><span class="sxs-lookup"><span data-stu-id="f6c04-119">The connection strings described in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help can be useful for programmers who create their own connection strings.</span></span> <span data-ttu-id="f6c04-120">Para acessar estas informações, na caixa de diálogo **Novo Alias** , pressione F1 ou clique em **Ajuda**.</span><span class="sxs-lookup"><span data-stu-id="f6c04-120">To access this information, in the **New Alias** dialog box, press F1, or click **Help**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6c04-121">Se um alias configurado estiver se conectando ao servidor ou à instância incorreta, desabilite e habilite novamente o protocolo de rede associado.</span><span class="sxs-lookup"><span data-stu-id="f6c04-121">If a configured alias is connecting to the wrong server or instance, disable and then reenable the associated network protocol.</span></span> <span data-ttu-id="f6c04-122">Fazendo isso, você limpa todas as informações de conexão em cache e permite que o cliente se conecte corretamente.</span><span class="sxs-lookup"><span data-stu-id="f6c04-122">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>  
  
#### <a name="to-delete-an-alias"></a><span data-ttu-id="f6c04-123">Para excluir um alias</span><span class="sxs-lookup"><span data-stu-id="f6c04-123">To delete an alias</span></span>  
  
1.  <span data-ttu-id="f6c04-124">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expanda **Configuração do SQL Server Native Client**e clique em **Aliases**.</span><span class="sxs-lookup"><span data-stu-id="f6c04-124">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, and then click **Aliases**.</span></span>  
  
2.  <span data-ttu-id="f6c04-125">No painel de detalhes, clique com o botão direito do mouse no alias que você deseja excluir e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="f6c04-125">In the details pane, right-click the alias that you want to delete, and then click **Delete**.</span></span>  
  
  
