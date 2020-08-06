---
title: Iniciar o utilitário sqlcmd
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 00d57437-7a29-4da1-b639-ee990db055fb
author: rothja
ms.author: jroth
ms.openlocfilehash: d71e6f140238599b3f22850ee9b63a0ee25d900b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570581"
---
# <a name="start-the-sqlcmd-utility"></a><span data-ttu-id="7d966-102">Iniciar o utilitário sqlcmd</span><span class="sxs-lookup"><span data-stu-id="7d966-102">Start the sqlcmd Utility</span></span>
  <span data-ttu-id="7d966-103">Para começar a usar o `sqlcmd`, você deve primeiro iniciar o utilitário e se conectar a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d966-103">To begin using `sqlcmd`, you must first launch the utility and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7d966-104">Você pode se conectar a uma instância padrão ou nomeada.</span><span class="sxs-lookup"><span data-stu-id="7d966-104">You can connect to either a default or named instance.</span></span> <span data-ttu-id="7d966-105">A primeira etapa é iniciar o utilitário `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="7d966-105">The first step is to start the `sqlcmd` utility.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d966-106">A Autenticação do Windows é o modo de autenticação padrão do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="7d966-106">Windows Authentication is the default authentication mode for `sqlcmd`.</span></span> <span data-ttu-id="7d966-107">Para usar a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , você deve especificar um nome de usuário e uma senha usando as opções **-U** e **-P** .</span><span class="sxs-lookup"><span data-stu-id="7d966-107">To use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must specify a user name and password by using the **-U** and **-P** options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d966-108"> Por padrão, o [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] é instalado como a instância nomeada **sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="7d966-108">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as the named instance **sqlexpress**.</span></span>  
  
 <span data-ttu-id="7d966-109">Caso você não tenha se conectado a essa instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] anteriormente, você pode ter de configurar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para aceitar conexões.</span><span class="sxs-lookup"><span data-stu-id="7d966-109">If you have not connected to this instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] before, you may have to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-default-instance-of-sql-server"></a><span data-ttu-id="7d966-110">Para iniciar o utilitário sqlcmd e conectar-se a uma instância padrão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d966-110">To start the sqlcmd utility and connect to a default instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="7d966-111">No menu **Iniciar** , clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="7d966-111">On the **Start** menu click **Run**.</span></span> <span data-ttu-id="7d966-112">Na caixa **Abrir** digite **cmd**e, então, clique em **OK** para abrir uma janela do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="7d966-112">In the **Open** box type **cmd**, and then click **OK** to open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="7d966-113">No prompt de comando, digite `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="7d966-113">At the command prompt, type `sqlcmd`.</span></span>  
  
3.  <span data-ttu-id="7d966-114">Pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="7d966-114">Press ENTER.</span></span>  
  
     <span data-ttu-id="7d966-115">Agora você tem uma conexão confiável com a instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo executada em seu computador.</span><span class="sxs-lookup"><span data-stu-id="7d966-115">You now have a trusted connection to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on your computer.</span></span>  
  
     <span data-ttu-id="7d966-116">**1>** é o `sqlcmd` prompt que especifica o número da linha.</span><span class="sxs-lookup"><span data-stu-id="7d966-116">**1>** is the `sqlcmd` prompt that specifies the line number.</span></span> <span data-ttu-id="7d966-117">A cada vez que você pressiona ENTER, aparece um número seguinte ao anterior.</span><span class="sxs-lookup"><span data-stu-id="7d966-117">Each time you press ENTER, the number increases by one.</span></span>  
  
4.  <span data-ttu-id="7d966-118">Para encerrar a `sqlcmd` sessão, digite `EXIT` no `sqlcmd` prompt.</span><span class="sxs-lookup"><span data-stu-id="7d966-118">To end the `sqlcmd` session, type `EXIT` at the `sqlcmd` prompt.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-named-instance-of-sql-server"></a><span data-ttu-id="7d966-119">Para iniciar o utilitário sqlcmd e se conectar a uma instância nomeada do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d966-119">To start the sqlcmd utility and connect to a named instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="7d966-120">Abra uma janela de prompt de comando e digite `sqlcmd -S` *myServer\instanceName*.</span><span class="sxs-lookup"><span data-stu-id="7d966-120">Open a Command Prompt window, and type `sqlcmd -S`*myServer\instanceName*.</span></span> <span data-ttu-id="7d966-121">Substitua *myServer\instanceName* pelo nome do computador e a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com a qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="7d966-121">Replace *myServer\instanceName* with the name of the computer and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to.</span></span>  
  
2.  <span data-ttu-id="7d966-122">Pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="7d966-122">Press ENTER.</span></span>  
  
     <span data-ttu-id="7d966-123">O `sqlcmd` prompt (1>) indica que você está conectado à instância especificada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d966-123">The `sqlcmd` prompt (1>) indicates that you are connected to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d966-124">As instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] digitadas são armazenadas em um buffer.</span><span class="sxs-lookup"><span data-stu-id="7d966-124">Entered [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are stored in a buffer.</span></span> <span data-ttu-id="7d966-125">Elas são executadas como um lote quando o comando GO é encontrado.</span><span class="sxs-lookup"><span data-stu-id="7d966-125">They are executed as a batch when the GO command is encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d966-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7d966-126">See Also</span></span>  
 [<span data-ttu-id="7d966-127">Executar arquivos de script Transact-SQL usando sqlcmd</span><span class="sxs-lookup"><span data-stu-id="7d966-127">Run Transact-SQL Script Files Using sqlcmd</span></span>](sqlcmd-run-transact-sql-script-files.md)  
  
  
