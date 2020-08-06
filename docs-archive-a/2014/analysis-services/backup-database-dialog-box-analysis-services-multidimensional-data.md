---
title: Caixa de diálogo backup Database (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Backup.f1
ms.assetid: 7811ce7d-6c37-4189-bfa6-ef36fb4932db
author: minewiskan
ms.author: owend
ms.openlocfilehash: 48cf094353c53213864dae656af94ae791442105
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571162"
---
# <a name="backup-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="758ac-102">Caixa de diálogo Banco de Dados de Backup (Analysis Services - Dados multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="758ac-102">Backup Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="758ac-103">Use a caixa de diálogo **Banco de Dados de Backup** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para fazer backup de um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] em um arquivo de backup usando o formato Analysis Services Backup File (.abf) do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="758ac-103">Use the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to back up an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="758ac-104">Para cada arquivo de backup, o usuário que executar o comando de backup deve ter permissão para gravar no local de backup especificado de cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="758ac-104">For each backup file, the user who runs the backup command must have permission to write to the backup location specified for each file.</span></span> <span data-ttu-id="758ac-105">Além disso, o usuário deve ter uma das seguintes funções: membro de uma função de servidor para a instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou membro de uma função de banco de dados com permissões de Controle total (Administrador) no banco de dados cujo backup será feito.</span><span class="sxs-lookup"><span data-stu-id="758ac-105">Also, the user must have one of the following roles: a member of a server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be backed up.</span></span>  
  
 <span data-ttu-id="758ac-106">**Para exibir a caixa de diálogo Banco de Dados de Backup**</span><span class="sxs-lookup"><span data-stu-id="758ac-106">**To display the Backup Database dialog box**</span></span>  
  
-   <span data-ttu-id="758ac-107">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], clique com o botão direito do mouse na pasta **Bancos de Dados** de uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou em um banco de dados no **Pesquisador de Objetos**e então clique em **Backup**.</span><span class="sxs-lookup"><span data-stu-id="758ac-107">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Backup**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="758ac-108">Opções</span><span class="sxs-lookup"><span data-stu-id="758ac-108">Options</span></span>  
 <span data-ttu-id="758ac-109">**Script**</span><span class="sxs-lookup"><span data-stu-id="758ac-109">**Script**</span></span>  
 <span data-ttu-id="758ac-110">Cria um script de backup baseado nas opções selecionadas na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="758ac-110">Creates a backup script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="758ac-111">O script de restauração é escrito na Linguagem de Scripts do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ASSL).</span><span class="sxs-lookup"><span data-stu-id="758ac-111">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="758ac-112">Clicar no ícone **Script** envia o script de backup a uma nova janela de consulta, por padrão.</span><span class="sxs-lookup"><span data-stu-id="758ac-112">Clicking the **Script** icon sends the backup script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="758ac-113">Clicar na seta **Script** exibe um menu que permite escolher para onde enviar o script de backup:</span><span class="sxs-lookup"><span data-stu-id="758ac-113">Clicking the **Script** arrow displays a menu that allows you to choose where to send the backup script:</span></span>  
  
-   <span data-ttu-id="758ac-114">Para uma nova janela de consulta (padrão).</span><span class="sxs-lookup"><span data-stu-id="758ac-114">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="758ac-115">Para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="758ac-115">To a file.</span></span>  
  
-   <span data-ttu-id="758ac-116">Para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="758ac-116">To the clipboard.</span></span>  
  
-   <span data-ttu-id="758ac-117">Para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="758ac-117">To a job.</span></span>  
  
 <span data-ttu-id="758ac-118">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="758ac-118">**Database**</span></span>  
 <span data-ttu-id="758ac-119">Exibe o nome do banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] atualmente selecionado.</span><span class="sxs-lookup"><span data-stu-id="758ac-119">Displays the name of the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="758ac-120">**Arquivo de backup**</span><span class="sxs-lookup"><span data-stu-id="758ac-120">**Backup file**</span></span>  
 <span data-ttu-id="758ac-121">Digite o caminho completo e nome do arquivo de backup a utilizar.</span><span class="sxs-lookup"><span data-stu-id="758ac-121">Type the full path and file name of the backup file to use.</span></span>  
  
 <span data-ttu-id="758ac-122">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="758ac-122">**Browse**</span></span>  
 <span data-ttu-id="758ac-123">Clique para exibir a caixa de diálogo **Salvar Arquivo Como** e selecionar o caminho e nome do arquivo de backup a utilizar.</span><span class="sxs-lookup"><span data-stu-id="758ac-123">Click to display the **Save File As** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="758ac-124">Para obter mais informações sobre a caixa de diálogo **Salvar Arquivo Como**, consulte [Caixa de diálogo Salvar Arquivo Como &#40;Analysis Services – Dados Multidimensionais&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="758ac-124">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="758ac-125">**Permitir substituição de arquivos**</span><span class="sxs-lookup"><span data-stu-id="758ac-125">**Allow file overwrite**</span></span>  
 <span data-ttu-id="758ac-126">Selecione para substituir um arquivo de backup existente ou arquivo de backup remoto, se houver um.</span><span class="sxs-lookup"><span data-stu-id="758ac-126">Select to overwrite an existing backup file or remote backup file, if one exists.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="758ac-127"> Se esta opção não for selecionada e existir o arquivo de backup especificado em **Arquivo de backup** ou um arquivo de backup remoto especificado em **Arquivo de backup remoto** , ocorre um erro.</span><span class="sxs-lookup"><span data-stu-id="758ac-127">If this option is not selected and the backup file specified in **Backup file** or a remote backup file specified in **Remote backup file** exists, an error occurs.</span></span>  
  
 <span data-ttu-id="758ac-128">**Aplicar compactação**</span><span class="sxs-lookup"><span data-stu-id="758ac-128">**Apply compression**</span></span>  
 <span data-ttu-id="758ac-129">Selecione para compactar os conteúdos do arquivo de backup e, se especificado, dos arquivos de backup remotos.</span><span class="sxs-lookup"><span data-stu-id="758ac-129">Select to compress the contents of the backup file and, if specified, remote backup files.</span></span>  
  
 <span data-ttu-id="758ac-130">**Criptografar arquivo de backup**</span><span class="sxs-lookup"><span data-stu-id="758ac-130">**Encrypt backup file**</span></span>  
 <span data-ttu-id="758ac-131">Selecione para criptografar o arquivo de backup usando a senha fornecida em **Senha**.</span><span class="sxs-lookup"><span data-stu-id="758ac-131">Select to encrypt the backup file using the password supplied in **Password**.</span></span>  
  
 <span data-ttu-id="758ac-132">**Senha**</span><span class="sxs-lookup"><span data-stu-id="758ac-132">**Password**</span></span>  
 <span data-ttu-id="758ac-133">Digite a senha a ser usada ao criptografar o arquivo de backup e, se especificados, arquivos de backup remotos.</span><span class="sxs-lookup"><span data-stu-id="758ac-133">Type the password to use when encrypting the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="758ac-134"> Esta opção só será habilitada se **Criptografar arquivo de backup** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="758ac-134">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="758ac-135">**Confirmar Senha**</span><span class="sxs-lookup"><span data-stu-id="758ac-135">**Confirm Password**</span></span>  
 <span data-ttu-id="758ac-136">Digite a senha que foi utilizada em **Senha** para confirmar a senha para o arquivo de backup e, se especificados, arquivos de backup remotos.</span><span class="sxs-lookup"><span data-stu-id="758ac-136">Type the password entered in **Password** to confirm the password for the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="758ac-137"> Esta opção só será habilitada se **Criptografar arquivo de backup** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="758ac-137">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="758ac-138">**Fazer backup de partição(ões) remota(s)**</span><span class="sxs-lookup"><span data-stu-id="758ac-138">**Backup remote partition(s)**</span></span>  
 <span data-ttu-id="758ac-139">Selecione para incluir informações de local e dados para partições remotas no arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="758ac-139">Select to include location information and data for remote partitions in the backup file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="758ac-140">Esta opção só será habilitada se o banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] atualmente selecionado usar partições remotas.</span><span class="sxs-lookup"><span data-stu-id="758ac-140">This option is enabled only if the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database uses remote partitions.</span></span>  
  
 <span data-ttu-id="758ac-141">**Local de backup da partição remota**</span><span class="sxs-lookup"><span data-stu-id="758ac-141">**Remote partition backup location**</span></span>  
 <span data-ttu-id="758ac-142">Exibe o local das partições remotas associadas com o banco de dados selecionado, como também o arquivo de backup remoto usado para fazer backup de dados e metadados para as partições remotas.</span><span class="sxs-lookup"><span data-stu-id="758ac-142">Displays the location of remote partitions associated with the selected database, as well as the remote backup file used to back up the data and metadata for the remote partitions.</span></span> <span data-ttu-id="758ac-143">As seguintes colunas estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="758ac-143">The following columns are available:</span></span>  
  
|<span data-ttu-id="758ac-144">Column</span><span class="sxs-lookup"><span data-stu-id="758ac-144">Column</span></span>|<span data-ttu-id="758ac-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="758ac-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="758ac-146">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="758ac-146">**Server**</span></span>|<span data-ttu-id="758ac-147">Exibe a instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que administra as partições remotas.</span><span class="sxs-lookup"><span data-stu-id="758ac-147">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that manages the remote partitions.</span></span>|  
|<span data-ttu-id="758ac-148">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="758ac-148">**Database**</span></span>|<span data-ttu-id="758ac-149">Exibe o banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que contém as partições remotas.</span><span class="sxs-lookup"><span data-stu-id="758ac-149">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that contains the remote partitions.</span></span>|  
|<span data-ttu-id="758ac-150">**Lista de Partições**</span><span class="sxs-lookup"><span data-stu-id="758ac-150">**Partition List**</span></span>|<span data-ttu-id="758ac-151">Exibe a lista de partições remotas contidas no banco de dados exibido em **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="758ac-151">Displays the list of remote partitions contained by the database displayed in **Database**.</span></span>|  
|<span data-ttu-id="758ac-152">**Arquivo de backup remoto**</span><span class="sxs-lookup"><span data-stu-id="758ac-152">**Remote backup file**</span></span>|<span data-ttu-id="758ac-153">Digite o caminho completo e o nome de arquivo do arquivo de backup remoto a ser usado, ou clique no botão de reticências (**...**) para exibir a caixa de diálogo **Salvar Arquivo Como** e selecionar o caminho e o nome de arquivo do arquivo de backup remoto a ser usado.</span><span class="sxs-lookup"><span data-stu-id="758ac-153">Type the full path and file name of the remote backup file to use, or click the ellipsis button (**...**) to display the **Save File As** dialog box and select the path and file name of the remote backup file to use.</span></span> <span data-ttu-id="758ac-154">Para obter mais informações sobre a caixa de diálogo **Salvar Arquivo Como**, consulte [Caixa de diálogo Salvar Arquivo Como &#40;Analysis Services – Dados Multidimensionais&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="758ac-154">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="758ac-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="758ac-155">See Also</span></span>  
 <span data-ttu-id="758ac-156">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="758ac-156">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="758ac-157">Backup e restauração de bancos de dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="758ac-157">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
