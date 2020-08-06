---
title: Salvar uma cópia de um pacote | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, saving
- packages [Integration Services], saving
- saving packages
- SSIS packages, saving
- SQL Server Integration Services packages, saving
ms.assetid: 21482a20-e420-4452-b7eb-8f9fa1929f31
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 02ee2374fddb7dbb6b17adc2a4a10707179c882d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680032"
---
# <a name="save-a-copy-of-a-package"></a><span data-ttu-id="ed6b1-102">Salvar uma cópia de um pacote</span><span class="sxs-lookup"><span data-stu-id="ed6b1-102">Save a Copy of a Package</span></span>
  <span data-ttu-id="ed6b1-103">Este procedimento descreve como salvar uma cópia de um pacote no sistema de arquivos, no armazenamento do pacote ou no banco de dados **msdb** no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed6b1-103">This procedure describes how to save a copy of a package to the file system, to the package store, or to the **msdb** database in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ed6b1-104">Ao especificar um local para salvar a cópia do pacote, também é possível atualizar o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-104">When you specify a location to save the package copy, you can also update the name of the package.</span></span>  
  
 <span data-ttu-id="ed6b1-105">O repositório do pacote pode incluir o banco de dados **msdb** e as pastas no sistema de arquivos, somente **msdb**, ou somente pastas no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-105">The package store can include both the **msdb** database and the folders in the file system, only **msdb**, or only folders in the file system.</span></span> <span data-ttu-id="ed6b1-106">No **msdb**, os pacotes são salvos na tabela **sysssispackages** .</span><span class="sxs-lookup"><span data-stu-id="ed6b1-106">In **msdb**, packages are saved to the **sysssispackages** table.</span></span> <span data-ttu-id="ed6b1-107">Esta tabela inclui uma coluna **folderid** que identifica a pasta lógica a qual o pacote pertence.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-107">This table includes a **folderid** column that identifies the logical folder to which the package belongs.</span></span> <span data-ttu-id="ed6b1-108">As pastas lógicas fornecem uma maneira útil de agrupar pacotes salvos em **msdb** da mesma forma que as pastas no sistema de arquivos fornecem uma maneira de agrupar pacotes salvos no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-108">The logical folders provide a useful way to group packages saved to **msdb** in the same way that folders in the file system provide a way to group packages saved to the file system.</span></span> <span data-ttu-id="ed6b1-109">As linhas na tabela **sysssispackagefolders** em **msdb** definem as pastas.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-109">Rows in the **sysssispackagefolders** table in **msdb** define the folders.</span></span>  
  
 <span data-ttu-id="ed6b1-110">Se **msdb** não for definido como parte do armazenamento do pacote, você poderá continuar a associar pacotes com pastas lógicas existentes ao selecionar o SQL Server na opção **Caminho do Pacote** .</span><span class="sxs-lookup"><span data-stu-id="ed6b1-110">If **msdb** is not defined as part of the package store, you can continue to associate packages with existing logical folders when you select SQL Server in the **Package Path** option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed6b1-111">O pacote deve ser aberto no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] antes que você possa salvar uma cópia do pacote.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-111">The package must be opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer before you can save a copy of the package.</span></span>  
  
### <a name="to-save-a-copy-of-a-package"></a><span data-ttu-id="ed6b1-112">Para salvar uma cópia de um pacote</span><span class="sxs-lookup"><span data-stu-id="ed6b1-112">To save a copy of a package</span></span>  
  
1.  <span data-ttu-id="ed6b1-113">No Gerenciador de Soluções, clique duas vezes no pacote do qual você quer salvar uma cópia.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-113">In Solution Explorer, double-click the package of which you want to save a copy.</span></span>  
  
2.  <span data-ttu-id="ed6b1-114">No menu **Arquivo**, clique em **Salvar Cópia de \<package file> como**.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-114">On the **File** menu, click **Save Copy of \<package file> As**.</span></span>  
  
3.  <span data-ttu-id="ed6b1-115">Na caixa de diálogo **Salvar Cópia do Pacote** , selecione um local de pacote na lista **Local dos pacotes** .</span><span class="sxs-lookup"><span data-stu-id="ed6b1-115">In the **Save Copy of Package** dialog box, select a package location in the **Package location** list.</span></span>  
  
4.  <span data-ttu-id="ed6b1-116">Se o local for **SQL Server** ou **Armazenamento de Pacotes SSIS**, forneça um nome de servidor.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-116">If the location is **SQL Server** or **SSIS Package Store**, provide a server name.</span></span>  
  
5.  <span data-ttu-id="ed6b1-117">Se for salvar o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], especifique o tipo de autenticação e, se estiver usando a Autenticação [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , forneça um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-117">If saving to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], specify the authentication type and, if using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and password.</span></span>  
  
6.  <span data-ttu-id="ed6b1-118">Para especificar o caminho do pacote, digite o caminho ou clique no botão Procurar **(...)** para especificar a localização do pacote.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-118">To specify the package path, either type the path or click the browse button **(...)** to specify the location of the package.</span></span> <span data-ttu-id="ed6b1-119">O nome padrão do pacote é Pacote.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-119">The default name of the package is Package.</span></span> <span data-ttu-id="ed6b1-120">Como opção, atualize o nome de pacote para um que atenda suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-120">Optionally, update the package name to one that suits your needs.</span></span>  
  
     <span data-ttu-id="ed6b1-121">Se você selecionar **SQL Server** como a opção de **Caminho do Pacote** , o caminho do pacote consistirá de pastas lógicas no **msdb** e o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-121">If you select **SQL Server** as the **Package Path** option, the package path consists of logical folders in **msdb** and the package name.</span></span> <span data-ttu-id="ed6b1-122">Por exemplo, se o pacote DownloadMonthlyData estiver associado à pasta Finance dentro da pasta MSDB (o nome padrão da pasta lógica raiz no **msdb**), o caminho do pacote chamado DownloadMonthlyData será MSDB/Finance/DownloadMonthlyData</span><span class="sxs-lookup"><span data-stu-id="ed6b1-122">For example, if the package DownloadMonthlyData is associated with the Finance folder within the MSDB folder (the default name of the root logical folder in **msdb**), the package path for the package named DownloadMonthlyData is MSDB/Finance/DownloadMonthlyData</span></span>  
  
     <span data-ttu-id="ed6b1-123">Se você selecionar **Armazenamento de Pacotes SSIS** como a opção de **Caminho do Pacote** , o caminho do pacote consistirá da pasta que o serviço Integration Services gerencia.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-123">If you select **SSIS Package Store** as the **Package Path** option, the package path consists of the folder that the Integration Services service manages.</span></span> <span data-ttu-id="ed6b1-124">Por exemplo, se o pacote UpdateDeductions estiver localizado na pasta Recursos Humanos dentro da pasta do sistema de arquivo que o serviço gerencia, o caminho do pacote será /Sistema de Arquivos/Recursos Humanos/UpdateDeductions; da mesma forma, se o pacote PostResumes estiver associado à pasta Recursos Humanos dentro da pasta MSDB, o caminho do pacote será MSDB/Recursos Humanos/PostResumes.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-124">For example, if the package UpdateDeductions is located in the HumanResources folder within the file system folder that the service manages, the package path is /File System/HumanResources/UpdateDeductions; likewise, if the package PostResumes is associated with the HumanResources folder within the MSDB folder, the package path is MSDB/HumanResources/PostResumes.</span></span>  
  
     <span data-ttu-id="ed6b1-125">Se você selecionar **Sistema de Arquivos** como a opção de **Caminho do Pacote** , o caminho do pacote será o local no sistema de arquivos e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-125">If you select **File System** as the **Package Path** option, the package path is the location in the file system and the file name.</span></span> <span data-ttu-id="ed6b1-126">Por exemplo, se o nome de pacote for UpdateDemographics, o caminho de pacote será C:\HumanResources\Quarterly\UpdateDemographics.dtsx.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-126">For example, if the package name is UpdateDemographics the package path is C:\HumanResources\Quarterly\UpdateDemographics.dtsx.</span></span>  
  
7.  <span data-ttu-id="ed6b1-127">Revise o nível de proteção do pacote.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-127">Review the package protection level.</span></span>  
  
8.  <span data-ttu-id="ed6b1-128">Como opção, clique no botão Procurar **(...)** ao lado da caixa **Nível de proteção** para alterar o nível de proteção.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-128">Optionally, click the browse button **(...)** by the **Protection level** box to change the protection level.</span></span>  
  
    -   <span data-ttu-id="ed6b1-129">Na caixa de diálogo **Nível de Proteção do Pacote** , selecione um nível de proteção diferente.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-129">In the **Package Protection Level** dialog box, select a different protection level.</span></span>  
  
    -   <span data-ttu-id="ed6b1-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-130">Click **OK**.</span></span>  
  
9. <span data-ttu-id="ed6b1-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed6b1-131">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6b1-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ed6b1-132">See Also</span></span>  
 <span data-ttu-id="ed6b1-133">[Integration Services &#40;os pacotes&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="ed6b1-133">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="ed6b1-134">Configurando o Serviço Integration Services &#40;Serviço SSIS#41;</span><span class="sxs-lookup"><span data-stu-id="ed6b1-134">Configuring the Integration Services Service &#40;SSIS Service&#41;</span></span>](service/integration-services-service-ssis-service.md)  
  
  
