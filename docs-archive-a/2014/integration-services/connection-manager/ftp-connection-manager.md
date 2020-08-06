---
title: Gerenciador de conexões FTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FTP connection manager
- connections [Integration Services], FTP
- connection managers [Integration Services], FTP
ms.assetid: c4f43455-29ca-44ba-ac7f-ea729b1daf93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a402f399ba4b7e69fc1d3cbca9dd64b32217ced1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679475"
---
# <a name="ftp-connection-manager"></a><span data-ttu-id="4d3ed-102">Gerenciador de conexões FTP</span><span class="sxs-lookup"><span data-stu-id="4d3ed-102">FTP Connection Manager</span></span>
  <span data-ttu-id="4d3ed-103">Um gerenciador de conexões de FTP habilita um pacote a conectar-se a um servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-103">An FTP connection manager enables a package to connect to a File Transfer Protocol (FTP) server.</span></span> <span data-ttu-id="4d3ed-104">A tarefa FTP que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui usa esse gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-104">The FTP task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="4d3ed-105">Quando você adiciona um gerenciador de conexões de FTP a um pacote, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] cria um gerenciador de conexões que pode ser resolvido como  uma conexão FTP em tempo de execução, define as propriedades do gerenciador de conexões e adiciona o gerenciador de conexões à coleção `Connections` do pacote.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-105">When you add an FTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that can be resolved as an FTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="4d3ed-106">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `FTP`.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-106">The `ConnectionManagerType` property of the connection manager is set to `FTP`.</span></span>  
  
 <span data-ttu-id="4d3ed-107">Você pode configurar um gerenciador de conexões de FTP adotando um dos procedimentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="4d3ed-107">You can configure the FTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="4d3ed-108">Especificando um nome e uma porta de servidor.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-108">Specify a server name and server port.</span></span>  
  
-   <span data-ttu-id="4d3ed-109">Especificando o acesso anônimo ou fornecendo um nome de usuário e uma senha para autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-109">Specify anonymous access, or provide a user name and a password for basic authentication.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4d3ed-110">O gerenciador de conexões de FTP dá suporte apenas para autenticação anônima e autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-110">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="4d3ed-111">Ele não suporta a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="4d3ed-112">Definindo o tempo limite, o número de repetições e a quantidade de dados a ser copiada de cada vez.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-112">Set the time-out, number of retries, and the amount of data to copy at a time.</span></span>  
  
-   <span data-ttu-id="4d3ed-113">Indicando se o gerenciador de conexões de FTP usa modo passivo ou ativo.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-113">Indicate whether the FTP connection manager uses passive or active mode.</span></span>  
  
 <span data-ttu-id="4d3ed-114">Dependendo da configuração do site de FTP ao qual o gerenciador de conexões de FTP se conectar, será necessário alterar os seguintes valores padrão do gerenciador de conexões:</span><span class="sxs-lookup"><span data-stu-id="4d3ed-114">Depending on the configuration of the FTP site to which the FTP connection manager connects, you may need to change the following default values of the connection manager:</span></span>  
  
-   <span data-ttu-id="4d3ed-115">A porta de servidor é definida como 21.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-115">The server port is set to 21.</span></span> <span data-ttu-id="4d3ed-116">Você deve especificar a porta que o site FTP escuta.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-116">You should specify the port that the FTP site listens to.</span></span>  
  
-   <span data-ttu-id="4d3ed-117">O nome de usuário é definido como "anônimo".</span><span class="sxs-lookup"><span data-stu-id="4d3ed-117">The user name is set to "anonymous".</span></span> <span data-ttu-id="4d3ed-118">Você deve fornecer as credenciais exigidas pelo site FTP.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-118">You should provide the credentials that the FTP site requires.</span></span>  
  
## <a name="activepassive-modes"></a><span data-ttu-id="4d3ed-119">Modos ativo/passivo</span><span class="sxs-lookup"><span data-stu-id="4d3ed-119">Active/Passive Modes</span></span>  
 <span data-ttu-id="4d3ed-120">Um gerenciador de conexões de FTP pode enviar e receber arquivos usando o modo ativo ou passivo.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-120">An FTP connection manager can send and receive files using either active mode or passive mode.</span></span> <span data-ttu-id="4d3ed-121">No modo ativo, o servidor inicia a conexão de dados e, no modo passivo, o cliente inicia a conexão de dados.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-121">In active mode, the server initiates the data connection, and in passive mode, the client initiates the data connection.</span></span>  
  
## <a name="configuration-of-the-ftp-connection-manager"></a><span data-ttu-id="4d3ed-122">Configuração do gerenciador de conexões FTP</span><span class="sxs-lookup"><span data-stu-id="4d3ed-122">Configuration of the FTP Connection Manager</span></span>  
 <span data-ttu-id="4d3ed-123">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4d3ed-124">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, consulte [Editor do Gerenciador de Conexões FTP](../ftp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ed-124">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [FTP Connection Manager Editor](../ftp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="4d3ed-125">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ed-125">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d3ed-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4d3ed-126">See Also</span></span>  
 <span data-ttu-id="4d3ed-127">[Tarefa FTP](../control-flow/ftp-task.md) </span><span class="sxs-lookup"><span data-stu-id="4d3ed-127">[FTP Task](../control-flow/ftp-task.md) </span></span>  
 [<span data-ttu-id="4d3ed-128">Conexões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4d3ed-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
