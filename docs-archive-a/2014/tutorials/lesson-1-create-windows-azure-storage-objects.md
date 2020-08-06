---
title: 'Lição 1: criar objetos de armazenamento do Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 74edd1fd-ab00-46f7-9e29-7ba3f1a446c5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d46c6d22ffd92dbf8035bff140960af8ef56122d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570400"
---
# <a name="lesson-1-create-azure-storage-objects"></a><span data-ttu-id="9d6f4-102">Lição 1: Criar objetos de Armazenamento do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="9d6f4-102">Lesson 1: Create Azure Storage Objects</span></span>
  <span data-ttu-id="9d6f4-103">Para que você possa criar backups do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no armazenamento em nuvem, primeiro crie uma conta de armazenamento e, depois, um contêiner de blob.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-103">Before you can create [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups on cloud storage, you must first create a storage account, and then a blob container.</span></span> <span data-ttu-id="9d6f4-104">A lição 1 orienta você pelas etapas de fazer logon na Portal de Gerenciamento do Azure, criando uma conta de armazenamento e um contêiner de BLOB.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-104">Lesson 1 walks you through the steps of Logging into the Azure Management Portal, creating a storage account and a blob container.</span></span>  
  
## <a name="create-a-storage-account"></a><span data-ttu-id="9d6f4-105">Criar uma conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="9d6f4-105">Create a storage Account</span></span>  
 <span data-ttu-id="9d6f4-106">Para criar uma conta de armazenamento do Portal de Gerenciamento do Azure, use as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="9d6f4-106">To create a storage account from the Azure Management Portal, use the following steps:</span></span>  
  
1.  <span data-ttu-id="9d6f4-107">Faça logon no portal de gerenciamento do Azure usando sua conta.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-107">Log in to the Azure Management Portal using your account.</span></span> <span data-ttu-id="9d6f4-108">Se você não tiver uma conta do Azure, [visite avaliação gratuita de 3 meses do Azure](https://go.microsoft.com/fwlink/?LinkId=271927).</span><span class="sxs-lookup"><span data-stu-id="9d6f4-108">If you do not have an Azure account, [visit Azure 3-Month free trial](https://go.microsoft.com/fwlink/?LinkId=271927).</span></span>  
  
     <span data-ttu-id="9d6f4-109">![Tela de logon do Azure](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Tela de logon do Azure")</span><span class="sxs-lookup"><span data-stu-id="9d6f4-109">![Azure Login Screen](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Azure Login Screen")</span></span>  
  
2.  <span data-ttu-id="9d6f4-110">Use as instruções passo a passo detalhadas [aqui](https://go.microsoft.com/fwlink/?LinkId=271926)para criar uma conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-110">Use the step by step instructions detailed [here](https://go.microsoft.com/fwlink/?LinkId=271926), to create a storage account.</span></span>  
  
3.  <span data-ttu-id="9d6f4-111">Procure a conta de armazenamento que você criou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-111">Browse to the storage account you created in previous step.</span></span> <span data-ttu-id="9d6f4-112">Na parte inferior central da página da Web, clique em **gerenciar chaves**.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-112">From the bottom center of the web page, click **MANAGE KEYS**.</span></span> <span data-ttu-id="9d6f4-113">As informações da conta serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-113">The account information is displayed.</span></span> <span data-ttu-id="9d6f4-114">Copie o nome da conta de armazenamento e as chaves de acesso.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-114">Copy the storage account name, and the Access Keys.</span></span> <span data-ttu-id="9d6f4-115">Essas informações são necessárias para criar credenciais armazenadas do SQL.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-115">This information is required to create SQL Stored Credentials.</span></span> <span data-ttu-id="9d6f4-116">O [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usará essas informações para acessar a conta de armazenamento e criar backups.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-116">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses this information to access the storage account and create backups.</span></span>  
  
     <span data-ttu-id="9d6f4-117">![Captura de tela de chaves de conta de armazenamento do Azure](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Captura de tela de chaves de conta de armazenamento do Azure")</span><span class="sxs-lookup"><span data-stu-id="9d6f4-117">![Screen shot of Azure Storage Account Keys](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Screen shot of Azure Storage Account Keys")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d6f4-118">Você também pode criar uma conta de armazenamento de modo programático usando APIs REST.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-118">You can also create a storage account programmatically using REST APIs.</span></span> <span data-ttu-id="9d6f4-119">Para obter mais informações, consulte [criar conta de armazenamento](https://go.microsoft.com/fwlink/?LinkId=271928).</span><span class="sxs-lookup"><span data-stu-id="9d6f4-119">For more information, see [Create Storage Account](https://go.microsoft.com/fwlink/?LinkId=271928).</span></span>  
  
### <a name="create-a-blob-container"></a><span data-ttu-id="9d6f4-120">Crie um contêiner de blob</span><span class="sxs-lookup"><span data-stu-id="9d6f4-120">Create a Blob Container</span></span>  
 <span data-ttu-id="9d6f4-121">Um contêiner fornece um agrupamento de conjunto de blobs.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-121">A container provides a grouping of a set of blobs.</span></span> <span data-ttu-id="9d6f4-122">Todos os blobs devem estar em um contêiner.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-122">All blobs must be in a container.</span></span> <span data-ttu-id="9d6f4-123">Uma conta pode conter um número ilimitado de contêineres, mas deve ter pelo menos um contêiner.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-123">An account can contain an unlimited number of containers, but must have at least one container.</span></span> <span data-ttu-id="9d6f4-124">Um contêiner pode armazenar um número ilimitado de blobs.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-124">A container can store an unlimited number of blobs.</span></span>  
  
 <span data-ttu-id="9d6f4-125">Para criar um contêiner, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="9d6f4-125">To create a Container, use the following steps:</span></span>  
  
1.  <span data-ttu-id="9d6f4-126">Selecione a conta de armazenamento, clique na guia **contêineres** e clique em **Adicionar contêiner** na parte inferior da tela que abre uma nova caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-126">Select the storage account, click the **CONTAINERS** tab and click **ADD CONTAINER** at the bottom of the screen which opens a new dialog box.</span></span>  
  
     <span data-ttu-id="9d6f4-127">![Criando um contêiner no Portal de Gerenciamento](../../2014/tutorials/media/backuptocloud.gif "Criando um contêiner no Portal de Gerenciamento")</span><span class="sxs-lookup"><span data-stu-id="9d6f4-127">![Creating a Container in the Management Portal](../../2014/tutorials/media/backuptocloud.gif "Creating a Container in the Management Portal")</span></span>  
  
2.  <span data-ttu-id="9d6f4-128">Insira um nome do contêiner.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-128">Enter the name for the container.</span></span> <span data-ttu-id="9d6f4-129">Anote o nome de contêiner que você especificou.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-129">Make a note of the container name you specified.</span></span> <span data-ttu-id="9d6f4-130">Essas informações são usadas na URL (caminho para o arquivo de backup) nas instruções T-SQL das lições 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-130">This information is used in the URL (path to backup file) in the T-SQL statements in lesson 3 and 4.</span></span>  
  
3.  <span data-ttu-id="9d6f4-131">Selecione privado para **tipo de acesso**.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-131">Select Private for **Access Type**.</span></span> <span data-ttu-id="9d6f4-132">É recomendável criar contêiner privados para proteger os arquivos de backup.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-132">We recommend creating private containers for securing your backup files.</span></span>  
  
     <span data-ttu-id="9d6f4-133">![Criando um novo contêiner de blob.](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Criando um novo contêiner de blob.")</span><span class="sxs-lookup"><span data-stu-id="9d6f4-133">![Creating a new blob container](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Creating a new blob container")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d6f4-134">A autenticação na conta de armazenamento é necessária para o backup e a restauração do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], mesmo se você optar por criar um contêiner público.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-134">Authentication to the storage account is required for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore even if you choose to create a public container.</span></span>  
    >   
    >  <span data-ttu-id="9d6f4-135">Você também pode criar uma contêiner de modo programático usando APIs REST.</span><span class="sxs-lookup"><span data-stu-id="9d6f4-135">You can also create a container programmatically using REST APIs.</span></span> <span data-ttu-id="9d6f4-136">Para obter mais informações, consulte [criar contêiner](https://go.microsoft.com/fwlink/?LinkId=271946).</span><span class="sxs-lookup"><span data-stu-id="9d6f4-136">For more information, see [Create Container](https://go.microsoft.com/fwlink/?LinkId=271946).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="9d6f4-137">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="9d6f4-137">Next Lesson</span></span>  
 <span data-ttu-id="9d6f4-138">[Lição 2: criar uma credencial de SQL Server](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="9d6f4-138">[Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
  
