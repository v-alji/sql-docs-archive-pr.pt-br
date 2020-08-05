---
title: Associar extensões de arquivo a um Editor de Códigos
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- file extensions [SQL Server]
- associating file extensions [SQL Server]
- Query Editor [SQL Server Management Studio], associating file extensions
ms.assetid: 193630f4-93de-4950-8f36-68702531f925
author: rothja
ms.author: jroth
ms.openlocfilehash: 0e8cfbc89892a99971e985ffd3ff10b99f89fe53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572468"
---
# <a name="associate-file-extensions-to-a-code-editor"></a><span data-ttu-id="036f1-102">Associar extensões de arquivo a um Editor de Códigos</span><span class="sxs-lookup"><span data-stu-id="036f1-102">Associate File Extensions to a Code Editor</span></span>
  <span data-ttu-id="036f1-103">Associar extensões de arquivo a um editor de código específico permite a você abrir um arquivo com o editor de código [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] apropriado quando você clicar duas vezes num arquivo em Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="036f1-103">Associating file extensions to a specific code editor allows you to open a file with the appropriate [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] code editor when you double-click a file in Windows Explorer.</span></span> <span data-ttu-id="036f1-104">As extensões normalmente usadas pelo [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], como .sql e .mdx, são associadas durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="036f1-104">The extensions commonly used by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], such as .sql and .mdx, are associated during installation.</span></span> <span data-ttu-id="036f1-105">As novas extensões de arquivos também devem estar associadas a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="036f1-105">New file extensions must also be associated to [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] in the file system.</span></span> <span data-ttu-id="036f1-106">Você pode usar este recurso para abrir arquivos criados com outros editores ou abrir arquivos que você renomeou, como backups de arquivos .sql que foram renomeados como .bak.</span><span class="sxs-lookup"><span data-stu-id="036f1-106">You can use this feature to open files created with other editors, or to open files you have renamed, such as backups of .sql files that were renamed .bak.</span></span>  
  
 <span data-ttu-id="036f1-107">Há duas etapas no processo.</span><span class="sxs-lookup"><span data-stu-id="036f1-107">There are two steps in the process.</span></span> <span data-ttu-id="036f1-108">Primeiro associe a extensão a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e então associe a extensão a um editor de código específico.</span><span class="sxs-lookup"><span data-stu-id="036f1-108">First associate the extension with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then associate the extension with a specific code editor.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-sql-server-management-studio"></a><span data-ttu-id="036f1-109">Para associar uma nova extensão de arquivo ao SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="036f1-109">To associate a new file extension with SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="036f1-110">No menu **Iniciar** , aponte para **Todos os Programas**, **Acessórios**e então clique em **Windows Explorer**.</span><span class="sxs-lookup"><span data-stu-id="036f1-110">On the **Start** menu, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="036f1-111">No Windows Explorer, no menu **Ferramentas** , clique em **Opções de Pasta**.</span><span class="sxs-lookup"><span data-stu-id="036f1-111">In Windows Explorer, on the **Tools** menu, click **Folder Options**.</span></span>  
  
3.  <span data-ttu-id="036f1-112">Na caixa de diálogo **Opções de Pasta** , na guia **Tipos de Arquivo** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="036f1-112">In the **Folder Options** dialog box, on the **File Types** tab, click **New**.</span></span>  
  
4.  <span data-ttu-id="036f1-113">Na caixa de diálogo **Criar Nova Extensão** , na caixa **Extensão de Arquivo** , digite a nova extensão de arquivo que você deseja associar e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="036f1-113">In the **Create New Extension** dialog box, in the **File Extension** box, type the new file extension that you want to associate, and then click **OK**.</span></span> <span data-ttu-id="036f1-114">Não inicie a extensão com um ponto.</span><span class="sxs-lookup"><span data-stu-id="036f1-114">Do not start the extension with a period.</span></span>  
  
5.  <span data-ttu-id="036f1-115">Na caixa **Tipos de arquivo registrados** , clique na sua extensão e clique em **Alterar**.</span><span class="sxs-lookup"><span data-stu-id="036f1-115">In the **Registered file** types box, click on your new extension, and then click **Change**.</span></span>  
  
6.  <span data-ttu-id="036f1-116">Na caixa de diálogo **Abrir Com**, clique em **SSMS – SQL Server Management Studio** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="036f1-116">In the **Open With** dialog box, click **SSMS - SQL Server Management Studio**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="036f1-117">Clique em **Fechar** para fechar a caixa de diálogo **Opções de Pasta** e feche o Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="036f1-117">Click **Close** to close the **Folder Options** dialog box, and then close Windows Explorer.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-a-code-editor-in-sql-server-management-studio"></a><span data-ttu-id="036f1-118">Para associar uma nova extensão de arquivo a um editor de código em SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="036f1-118">To associate a new file extension with a code editor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="036f1-119">Em [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="036f1-119">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], from the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="036f1-120">Na caixa de diálogo **Opções** , clique em **Editor de Texto**e clique em **Extensão de Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="036f1-120">In the **Options** dialog box, click **Text Editor**, and then click **File Extension**.</span></span>  
  
3.  <span data-ttu-id="036f1-121">Na caixa **Extensão** , digite sua nova extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="036f1-121">In the **Extension** box, type your new file extension.</span></span>  
  
4.  <span data-ttu-id="036f1-122">Na caixa **Editor** , clique no editor de código que você deseja usar para abrir este tipo de arquivo, clique em **Adicionar**e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="036f1-122">In the **Editor** box, click the code editor that you wish to use to open this file type, click **Add**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="036f1-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="036f1-123">See Also</span></span>  
 [<span data-ttu-id="036f1-124">Utilitário de Ssms</span><span class="sxs-lookup"><span data-stu-id="036f1-124">Ssms Utility</span></span>](../../ssms/ssms-utility.md)  
  
  
