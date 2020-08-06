---
title: Caixa de diálogo Restore Database (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Restore.f1
ms.assetid: a3990d47-55e2-424e-8eac-87edc937e806
author: minewiskan
ms.author: owend
ms.openlocfilehash: f45a41eb10e81e1cfe1100045cc4d00353cb11fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686409"
---
# <a name="restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="c5ad9-102">Caixa de diálogo Restaurar Banco de Dados (Analysis Services - Dados multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="c5ad9-102">Restore Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="c5ad9-103">Use a caixa de diálogo **Restaurar Banco de Dados** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para restaurar um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] de um arquivo de backup utilizando o formato [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf).</span><span class="sxs-lookup"><span data-stu-id="c5ad9-103">Use the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database from a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c5ad9-104">Para cada arquivo de backup, o usuário que executar o comando de restauração deve ter permissão para ler no local de backup especificado para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5ad9-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="c5ad9-105">Para restaurar um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que não esteja instalado no servidor, o usuário também deve ser membro da função de servidor dessa instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5ad9-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="c5ad9-106">Para substituir um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , o usuário deve ter uma das seguintes funções: membro da função de servidor da instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou membro de uma função de banco de dados com permissões de Controle Total (Administrador) no banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="c5ad9-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5ad9-107">Após restaurar um banco de dados existente, o usuário que o restaurou poderá perder o acesso ao banco de dados restaurado.</span><span class="sxs-lookup"><span data-stu-id="c5ad9-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="c5ad9-108">Essa perda de acesso pode ocorrer se, no momento da execução do backup, o usuário não for membro da função de servidor, nem membro da função de banco de dados com permissões de Controle total (Administrador).</span><span class="sxs-lookup"><span data-stu-id="c5ad9-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="c5ad9-109">**Para exibir a caixa de diálogo Restaurar Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="c5ad9-109">**To display the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="c5ad9-110">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], clique com o botão direito do mouse na pasta **Bancos de Dados** de uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou em um banco de dados em **Pesquisador de Objetos**e então clique em **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="c5ad9-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Restore**.</span></span>  
  
 <span data-ttu-id="c5ad9-111">A caixa de diálogo **Restaurar Banco de Dados** contém as páginas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c5ad9-111">The **Restore Database** dialog box contains the following pages.</span></span>  
  
## <a name="pages"></a><span data-ttu-id="c5ad9-112">Pages (Páginas)</span><span class="sxs-lookup"><span data-stu-id="c5ad9-112">Pages</span></span>  
 <span data-ttu-id="c5ad9-113">**Geral**</span><span class="sxs-lookup"><span data-stu-id="c5ad9-113">**General**</span></span>  
 <span data-ttu-id="c5ad9-114">Use esta página para selecionar o banco de dados a restaurar, o arquivo de backup do qual restaurar o banco de dados e também as opções gerais e senha a utilizar ao restaurar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c5ad9-114">Use this page to select the database to restore, the backup file from which to restore the database, as well as the general options and password to use while restoring the database.</span></span> <span data-ttu-id="c5ad9-115">Para obter mais informações sobre essa página, consulte [Geral &#40;caixa de diálogo Restaurar Banco de Dados&#41; &#40;Analysis Services – Dados Multidimensionais&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="c5ad9-115">For more information about this page, see [General &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="c5ad9-116">**Partições**</span><span class="sxs-lookup"><span data-stu-id="c5ad9-116">**Partitions**</span></span>  
 <span data-ttu-id="c5ad9-117">Use esta página para restaurar partições locais a locais especificados e restaurar partições remotas de arquivos de backup remotos.</span><span class="sxs-lookup"><span data-stu-id="c5ad9-117">Use this page to restore local partitions to specified locations, and to restore remote partitions from remote backup files.</span></span> <span data-ttu-id="c5ad9-118">Para obter mais informações sobre essa página, consulte [Partições &#40;caixa de diálogo Restaurar Banco de Dados&#41; &#40;Analysis Services – Dados Multidimensionais&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="c5ad9-118">For more information about this page, see [Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5ad9-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c5ad9-119">See Also</span></span>  
 <span data-ttu-id="c5ad9-120">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="c5ad9-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="c5ad9-121">Backup e restauração de bancos de dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c5ad9-121">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
