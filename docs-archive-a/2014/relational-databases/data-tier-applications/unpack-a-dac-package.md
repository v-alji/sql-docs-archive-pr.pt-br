---
title: Desempacotar um pacote de DAC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- wizard [DAC], unpack
- data-tier application [SQL Server], unpack
- How to [DAC], unpack
- unpack DAC
ms.assetid: 697b69b3-f157-4e22-ac4e-f65c5fc2d0ad
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ba0930f79a47696a6c9a9c1bfe028316601f64b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583624"
---
# <a name="unpack-a-dac-package"></a><span data-ttu-id="84c3f-102">Desempacotar um pacote de DAC</span><span class="sxs-lookup"><span data-stu-id="84c3f-102">Unpack a DAC Package</span></span>
  <span data-ttu-id="84c3f-103">Use a caixa de diálogo Desempacotar Aplicativo da Camada de Dados para descompactar os scripts e arquivos de um pacote de DAC (aplicativo da camada de dados).</span><span class="sxs-lookup"><span data-stu-id="84c3f-103">Use the Unpack Data-tier Application dialog box to unzip the scripts and files from a data-tier application (DAC) package.</span></span> <span data-ttu-id="84c3f-104">Os scripts e arquivos são colocados em uma pasta onde podem ser examinados antes do pacote ser usado para implantar o DAC em um sistema de produção.</span><span class="sxs-lookup"><span data-stu-id="84c3f-104">The scripts and files are placed in a folder where they can be reviewed before the package is used to deploy the DAC into a production system.</span></span> <span data-ttu-id="84c3f-105">O conteúdo de um DAC também pode ser comparado com o conteúdo de outro pacote desempacotado em outra pasta.</span><span class="sxs-lookup"><span data-stu-id="84c3f-105">The contents of one DAC can also be compared with the contents of another package unpacked to another folder.</span></span>  
  
1.  <span data-ttu-id="84c3f-106">**Antes de começar:**  [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="84c3f-106">**Before you begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="84c3f-107">**Para desempacotar um DAC usando:**  [Caixa de Diálogo Desempacotar Aplicativo da Camada de Dados](#UnpackDACDial), [Examinar o Conteúdo de um Pacote de DAC](#ExamDACPack)</span><span class="sxs-lookup"><span data-stu-id="84c3f-107">**To unpack a DAC, using:**  [Unpack Data-tier Application Dialog](#UnpackDACDial), [Examine the Contents of a DAC Package](#ExamDACPack)</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="84c3f-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="84c3f-108">Security</span></span>  
 <span data-ttu-id="84c3f-109">Recomendamos não implantar um pacote de DAC de origens desconhecidas ou não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="84c3f-109">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="84c3f-110">Como os DACs podem conter código mal-intencionado que pode executar código [!INCLUDE[tsql](../../includes/tsql-md.md)] sem finalidade ou provocar erros modificando o esquema.</span><span class="sxs-lookup"><span data-stu-id="84c3f-110">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="84c3f-111">Antes de usar um DAC de uma origem desconhecida ou não confiável, implante-o em uma instância de teste isolada do [!INCLUDE[ssDE](../../includes/ssde-md.md)], desempacote o DAC e examine o código, como procedimentos armazenados ou outro código definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="84c3f-111">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], unpack the DAC and examine the code, such as stored procedures or other user-defined code.</span></span>  
  
##  <a name="unpack-data-tier-application-dialog"></a><a name="UnpackDACDial"></a> <span data-ttu-id="84c3f-112">Caixa de diálogo Desempacotar Aplicativo da Camada de Dados</span><span class="sxs-lookup"><span data-stu-id="84c3f-112">Unpack Data-tier Application Dialog</span></span>  
 <span data-ttu-id="84c3f-113">**Para desempacotar um arquivo do pacote de DAC**</span><span class="sxs-lookup"><span data-stu-id="84c3f-113">**To Unpack a DAC Package File**</span></span>  
  
-   <span data-ttu-id="84c3f-114">No **Windows Explorer**, navegue até a localização de um arquivo de pacote de DAC (.dacpac).</span><span class="sxs-lookup"><span data-stu-id="84c3f-114">In **Windows Explorer**, navigate to the location of a DAC package (.dacpac) file.</span></span>  
  
-   <span data-ttu-id="84c3f-115">Use um destes dois métodos para abrir a caixa de diálogo Desempacotar Aplicativo da Camada de Dados:</span><span class="sxs-lookup"><span data-stu-id="84c3f-115">Use one of these two methods to open the Unpack Data-tier Application dialog:</span></span>  
  
    1.  <span data-ttu-id="84c3f-116">Clique com o botão direito do mouse no arquivo de pacote de DAC (.dacpac) e selecione **Desempacotar**.</span><span class="sxs-lookup"><span data-stu-id="84c3f-116">Right-click the DAC package (.dacpac) file and select **Unpack**.</span></span>  
  
    2.  <span data-ttu-id="84c3f-117">Clique duas vezes no arquivo do pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="84c3f-117">Double-click the DAC package file.</span></span>  
  
-   <span data-ttu-id="84c3f-118">Conclua os diálogos:</span><span class="sxs-lookup"><span data-stu-id="84c3f-118">Complete the dialogs:</span></span>  
  
    -   [<span data-ttu-id="84c3f-119">Desempacotar Arquivo de Pacote de DAC do Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="84c3f-119">Unpack Microsoft SQL Server DAC Package File</span></span>](#Unpack)  
  
    -   [<span data-ttu-id="84c3f-120">Procurar Pasta</span><span class="sxs-lookup"><span data-stu-id="84c3f-120">Browse for Folder</span></span>](#Browse)  
  
###  <a name="unpack-microsoft-sql-server-dac-package-file"></a><a name="Unpack"></a> <span data-ttu-id="84c3f-121">Desempacotar Arquivo de Pacote de DAC do Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="84c3f-121">Unpack Microsoft SQL Server DAC Package File</span></span>  
 <span data-ttu-id="84c3f-122">Use esta página para especificar a pasta de destino na qual colocar os arquivos desempacotados e execute a operação e desempacotamento.</span><span class="sxs-lookup"><span data-stu-id="84c3f-122">Use this page to specify the destination folder in which to place the unpacked files, and then run the unpack operation.</span></span>  
  
 <span data-ttu-id="84c3f-123">**Os arquivos serão desempacotados nesta pasta:** – Especifique o caminho completo da pasta para os arquivos desempacotados.</span><span class="sxs-lookup"><span data-stu-id="84c3f-123">**Files will be unpacked to this folder:** - Specify the full path to the folder for the unpacked files.</span></span> <span data-ttu-id="84c3f-124">Se a pasta existir e você conhecer o caminho completo, digite o caminho na caixa.</span><span class="sxs-lookup"><span data-stu-id="84c3f-124">If the folder exists and you know the full path, type the path in the box.</span></span> <span data-ttu-id="84c3f-125">Caso contrário, clique no botão **Procurar** para navegar para uma pasta ou criar uma nova pasta.</span><span class="sxs-lookup"><span data-stu-id="84c3f-125">If not, click the **Browse** button to navigate to a folder or create a new folder.</span></span>  
  
 <span data-ttu-id="84c3f-126">**Procurar** – Abre a página **Procurar Pasta** , em que é possível escolher uma pasta navegando pela hierarquia de arquivos ou criar uma nova pasta.</span><span class="sxs-lookup"><span data-stu-id="84c3f-126">**Browse** - Opens the **Browse for Folder** page where you can choose a folder by navigating the file hierarchy, or create a new folder.</span></span>  
  
 <span data-ttu-id="84c3f-127">**Desempacotar** – Inicia a operação de desempacotamento.</span><span class="sxs-lookup"><span data-stu-id="84c3f-127">**Unpack** - Starts the unpack operation.</span></span>  
  
 <span data-ttu-id="84c3f-128">**Cancelar** – Encerra a caixa de diálogo sem desempacotar o pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="84c3f-128">**Cancel** - Terminates the dialog box without unpacking the DAC package.</span></span>  
  
###  <a name="browse-for-folder"></a><a name="Browse"></a> <span data-ttu-id="84c3f-129">Procurar Pasta</span><span class="sxs-lookup"><span data-stu-id="84c3f-129">Browse for Folder</span></span>  
 <span data-ttu-id="84c3f-130">Use esta página para escolher a pasta de destino para a operação de desempacotamento.</span><span class="sxs-lookup"><span data-stu-id="84c3f-130">Use this page to choose the destination folder for the unpack operation.</span></span> <span data-ttu-id="84c3f-131">Como opção, você também pode criar uma nova pasta.</span><span class="sxs-lookup"><span data-stu-id="84c3f-131">Optionally, you can also create a new folder.</span></span>  
  
 <span data-ttu-id="84c3f-132">**Lista de pastas** – Exibe a hierarquia de arquivos de seu computador.</span><span class="sxs-lookup"><span data-stu-id="84c3f-132">**Folder list** - Displays the file hierarchy for your computer.</span></span> <span data-ttu-id="84c3f-133">Expanda os nós para navegar para a pasta na qual desempacotar o pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="84c3f-133">Expand the nodes to navigate to the folder in which to unpack the DAC package.</span></span> <span data-ttu-id="84c3f-134">Clique na pasta e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="84c3f-134">Click on the folder and then click **OK**.</span></span>  
  
 <span data-ttu-id="84c3f-135">**Criar Nova Pasta** – Abre uma caixa de diálogo na qual é possível especificar o nome de uma nova pasta a ser criada na pasta selecionada atualmente na hierarquia de pastas.</span><span class="sxs-lookup"><span data-stu-id="84c3f-135">**Make New Folder** - Opens a dialog in which you can specify the name for a new folder to be created in the folder you have currently selected in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="84c3f-136">**OK** – Coloca o caminho para a pasta selecionada na caixa **Os arquivos serão desempacotados nesta pasta** da página **Desempacotar Arquivo de Pacote de DAC** e retorna para a página.</span><span class="sxs-lookup"><span data-stu-id="84c3f-136">**OK** - Places the path to the folder you selected in the **Files will be unpacked to this folder** box of the **Unpack DAC Package File** page and returns you to that page.</span></span>  
  
 <span data-ttu-id="84c3f-137">**Cancelar** – Encerra a caixa de diálogo sem selecionar uma pasta.</span><span class="sxs-lookup"><span data-stu-id="84c3f-137">**Cancel** - Terminates the dialog box without selecting a folder.</span></span>  
  
##  <a name="examine-the-contents-of-a-dac-package"></a><a name="ExamDACPack"></a> <span data-ttu-id="84c3f-138">Examinar o Conteúdo de um Pacote de DAC</span><span class="sxs-lookup"><span data-stu-id="84c3f-138">Examine the Contents of a DAC Package</span></span>  
 <span data-ttu-id="84c3f-139">Depois de desempacotar o pacote, você poderá examinar os arquivos gerados pela caixa de diálogo **Desempacotar Aplicativo da Camada de Dados** .</span><span class="sxs-lookup"><span data-stu-id="84c3f-139">After unpacking the package, you can examine the files produced by the **Unpack Data-tier Application** dialog.</span></span> <span data-ttu-id="84c3f-140">A caixa de diálogo cria os arquivos a seguir na pasta de destino selecionada:</span><span class="sxs-lookup"><span data-stu-id="84c3f-140">The dialog box builds the following files in the selected destination folder:</span></span>  
  
1.  <span data-ttu-id="84c3f-141">Um script do Transact-SQL que contém as instruções para criar os objetos definidos no DAC.</span><span class="sxs-lookup"><span data-stu-id="84c3f-141">A Transact-SQL script that contains the statements for creating the objects defined in the DAC.</span></span> <span data-ttu-id="84c3f-142">O nome do arquivo é *DACName*.sql, em que *DACName* é o nome do DAC.</span><span class="sxs-lookup"><span data-stu-id="84c3f-142">The file name is *DACName*.sql, where *DACName* is the name of the DAC.</span></span>  
  
2.  <span data-ttu-id="84c3f-143">Todos os arquivos XML do pacote.</span><span class="sxs-lookup"><span data-stu-id="84c3f-143">All XML files from the package.</span></span>  
  
3.  <span data-ttu-id="84c3f-144">Todos os arquivos da seção Arquivos Extras do DAC, como os arquivos de pré-implantação ou de pós-implantação do DAC.</span><span class="sxs-lookup"><span data-stu-id="84c3f-144">All files from the Extra Files section of the DAC, such as the DAC pre-deployment or post-deployment files.</span></span>  
  
 <span data-ttu-id="84c3f-145">Para obter mais informações, consulte [Validate a DAC Package](validate-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="84c3f-145">For more information, see [Validate a DAC Package](validate-a-dac-package.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c3f-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84c3f-146">See Also</span></span>  
 <span data-ttu-id="84c3f-147">[Aplicativos da Camada de Dados](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="84c3f-147">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="84c3f-148">[Implantar um aplicativo da camada de dados](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="84c3f-148">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="84c3f-149">Atualizar um aplicativo da camada de dados</span><span class="sxs-lookup"><span data-stu-id="84c3f-149">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
  
  
