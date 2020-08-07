---
title: Geral (caixa de diálogo Restore Database) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.restoredbdialog.f1
ms.assetid: 319e7ef5-c9c7-4e50-8690-02a90aed006f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25a49e17227fc2ed6b7b18d2e0964cd8812cbdcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583228"
---
# <a name="general-restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="b98aa-102">Geral (caixa de diálogo Restaurar Banco de Dados) (Analysis Services - Dados multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="b98aa-102">General (Restore Database Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b98aa-103">Use a página **Geral** da caixa de diálogo **Restaurar Banco de Dados** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para especificar o arquivo de backup e configurações gerais para usar ao restaurar um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b98aa-103">Use the **General** page of the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to specify the backup file and general settings to use when restoring an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b98aa-104">Para cada arquivo de backup, o usuário que executar o comando de restauração deve ter permissão para ler no local de backup especificado para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="b98aa-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="b98aa-105">Para restaurar um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que não esteja instalado no servidor, o usuário também deve ser membro da função de servidor dessa instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b98aa-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="b98aa-106">Para substituir um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , o usuário deve ter uma das seguintes funções: membro da função de servidor da instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou membro de uma função de banco de dados com permissões de Controle Total (Administrador) no banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="b98aa-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b98aa-107">Após restaurar um banco de dados existente, o usuário que o restaurou poderá perder o acesso ao banco de dados restaurado.</span><span class="sxs-lookup"><span data-stu-id="b98aa-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="b98aa-108">Essa perda de acesso pode ocorrer se, no momento da execução do backup, o usuário não for membro da função de servidor, nem membro da função de banco de dados com permissões de Controle total (Administrador).</span><span class="sxs-lookup"><span data-stu-id="b98aa-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="b98aa-109">**Para exibir a página Geral na caixa de diálogo Restaurar Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="b98aa-109">**To display the General page in the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="b98aa-110">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], clique com o botão direito do mouse na pasta **Bancos de Dados** de uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou em um banco de dados no **Pesquisador de Objetos**, clique em **Restaurar**e então, em **Selecionar uma página**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="b98aa-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, click **Restore**, and then under **Select a page**, click **General**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b98aa-111">Opções</span><span class="sxs-lookup"><span data-stu-id="b98aa-111">Options</span></span>  
 <span data-ttu-id="b98aa-112">**Script**</span><span class="sxs-lookup"><span data-stu-id="b98aa-112">**Script**</span></span>  
 <span data-ttu-id="b98aa-113">Cria um script de restauração baseado nas opções selecionadas na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b98aa-113">Creates a restore script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="b98aa-114">O script de restauração é escrito na Linguagem de Scripts do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ASSL).</span><span class="sxs-lookup"><span data-stu-id="b98aa-114">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="b98aa-115">Clicar no ícone **Script** envia o script de restauração a uma nova janela de consulta, por padrão.</span><span class="sxs-lookup"><span data-stu-id="b98aa-115">Clicking the **Script** icon sends the restore script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="b98aa-116">Clicar na seta **Script** exibe um menu que permite escolher para onde enviar o script de restauração:</span><span class="sxs-lookup"><span data-stu-id="b98aa-116">Clicking the **Script** arrow displays a menu that allows you to choose where to send the restore script:</span></span>  
  
-   <span data-ttu-id="b98aa-117">Para uma nova janela de consulta (padrão).</span><span class="sxs-lookup"><span data-stu-id="b98aa-117">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="b98aa-118">Para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b98aa-118">To a file.</span></span>  
  
-   <span data-ttu-id="b98aa-119">Para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b98aa-119">To the clipboard.</span></span>  
  
-   <span data-ttu-id="b98aa-120">Para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="b98aa-120">To a job.</span></span>  
  
 <span data-ttu-id="b98aa-121">**Restaurar banco de dados**</span><span class="sxs-lookup"><span data-stu-id="b98aa-121">**Restore database**</span></span>  
 <span data-ttu-id="b98aa-122">Selecione o banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a restaurar.</span><span class="sxs-lookup"><span data-stu-id="b98aa-122">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to restore.</span></span>  
  
 <span data-ttu-id="b98aa-123">**De arquivo de backup**</span><span class="sxs-lookup"><span data-stu-id="b98aa-123">**From backup file**</span></span>  
 <span data-ttu-id="b98aa-124">Selecione o arquivo de backup do qual restaurar o banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selecionado.</span><span class="sxs-lookup"><span data-stu-id="b98aa-124">Select the backup file from which to restore the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="b98aa-125">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="b98aa-125">**Browse**</span></span>  
 <span data-ttu-id="b98aa-126">Clique para exibir a caixa de diálogo **Localizar Arquivos de Banco de Dados** e selecionar o caminho e nome do arquivo de backup a utilizar.</span><span class="sxs-lookup"><span data-stu-id="b98aa-126">Click to display the **Locate Database Files** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="b98aa-127">Para obter mais informações sobre a caixa de diálogo **Localizar Arquivos de Banco de Dados**, consulte [Caixa de diálogo Localizar Arquivos de Banco de Dados &#40;Analysis Services – Dados Multidimensionais&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b98aa-127">For more information about the **Locate Database Files** dialog box, see [Locate Database Files Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="b98aa-128">**Permitir substituição de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="b98aa-128">**Allow database overwrite**</span></span>  
 <span data-ttu-id="b98aa-129">Selecione para permitir que o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] restaure os conteúdos do arquivo de backup selecionado em lugar de quaisquer objetos existentes no banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selecionado.</span><span class="sxs-lookup"><span data-stu-id="b98aa-129">Select to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to restore the contents of the selected backup file over any existing objects in the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="b98aa-130">**Incluir informações de segurança**</span><span class="sxs-lookup"><span data-stu-id="b98aa-130">**Include security information**</span></span>  
 <span data-ttu-id="b98aa-131">Selecione para copiar quaisquer informações de segurança armazenadas no arquivo de backup para o banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b98aa-131">Select to copy any security information stored in the backup file to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="b98aa-132">Se esta opção for selecionada, você poderá escolher a quantidade de informações de segurança na lista suspensa habilitada ao selecionar esta opção.</span><span class="sxs-lookup"><span data-stu-id="b98aa-132">If this option is selected, you can choose the amount of security information from the drop-down list enabled by selecting this option.</span></span> <span data-ttu-id="b98aa-133">As seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b98aa-133">The following options are available:</span></span>  
  
|<span data-ttu-id="b98aa-134">Opção</span><span class="sxs-lookup"><span data-stu-id="b98aa-134">Option</span></span>|<span data-ttu-id="b98aa-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="b98aa-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b98aa-136">**Copiar tudo**</span><span class="sxs-lookup"><span data-stu-id="b98aa-136">**Copy All**</span></span>|<span data-ttu-id="b98aa-137">Restaura as funções de banco de dados contidas no arquivo de backup, assim como as contas de usuário associadas às funções.</span><span class="sxs-lookup"><span data-stu-id="b98aa-137">Restores the database roles contained in the backup file, as well as the user accounts associated with the roles.</span></span>|  
|<span data-ttu-id="b98aa-138">**Ignorar Associação**</span><span class="sxs-lookup"><span data-stu-id="b98aa-138">**Skip Membership**</span></span>|<span data-ttu-id="b98aa-139">Restaura as funções de banco de dados contidas no arquivo de backup, mas não restaura as contas de usuário associadas às funções.</span><span class="sxs-lookup"><span data-stu-id="b98aa-139">Restores the database roles contained in the backup file, but does not restore the user accounts associated with the roles.</span></span>|  
  
 <span data-ttu-id="b98aa-140">**Senha**</span><span class="sxs-lookup"><span data-stu-id="b98aa-140">**Password**</span></span>  
 <span data-ttu-id="b98aa-141">Se o arquivo de backup estiver criptografado, digite a senha usada para criptografar o arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="b98aa-141">If the backup file is encrypted, type the password used to encrypt the backup file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b98aa-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b98aa-142">See Also</span></span>  
 <span data-ttu-id="b98aa-143">[Caixa de diálogo Restaurar Banco de dados &#40;Analysis Services-&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b98aa-143">[Restore Database Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="b98aa-144">[Caixa de diálogo partições &#40;Restore Database&#41; &#40;Analysis Services-dados multidimensionais&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b98aa-144">[Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="b98aa-145">Backup e restauração de bancos de dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b98aa-145">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
