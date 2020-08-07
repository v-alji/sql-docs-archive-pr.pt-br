---
title: Fazer check-in de arquivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckInDialog
helpviewer_keywords:
- checking in files
ms.assetid: 0657a387-8411-4406-bef9-d262a5bfa269
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 070c1dfa5dd057cf777980f7022752a97a4dc84c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575369"
---
# <a name="check-in-files"></a><span data-ttu-id="d3570-102">Fazer check-in de arquivos</span><span class="sxs-lookup"><span data-stu-id="d3570-102">Check In Files</span></span>
  <span data-ttu-id="d3570-103">Para tornar arquivos com controle do código-fonte disponíveis para outros usuários, você deve fazer o check-in dos arquivos no controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="d3570-103">To make source-controlled files that you have modified available to other users, you must check the files into source control.</span></span> <span data-ttu-id="d3570-104">Quando você faz check-in de um arquivo, essa versão é salva no provedor de controle do código-fonte e torna-se a versão mais recente do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3570-104">When you check in a file, the version you check in is written to the source control provider and becomes the latest version of the file.</span></span>  
  
 <span data-ttu-id="d3570-105">É possível usar o comando **Check-in** para fazer check-in dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="d3570-105">You can use the **Check In** command to check in files.</span></span> <span data-ttu-id="d3570-106">Se você usar esse comando para fazer check-in de uma solução ou projeto, todos os arquivos da solução ou do projeto também farão check-in.</span><span class="sxs-lookup"><span data-stu-id="d3570-106">If you use this command to check in a solution or project, all the files in the solution or project are also checked in.</span></span> <span data-ttu-id="d3570-107">Entretanto, fazer o check-in de um arquivo de código-fonte individual não resulta no check-in do projeto ou da solução a que ele pertence.</span><span class="sxs-lookup"><span data-stu-id="d3570-107">However, checking in an individual source code file does not result in the check-in of the project or solution to which it belongs.</span></span>  
  
### <a name="to-check-in-a-file"></a><span data-ttu-id="d3570-108">Para fazer check-in de um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3570-108">To check in a file</span></span>  
  
1.  <span data-ttu-id="d3570-109">No Gerenciador de Soluções, clique com o botão direito do mouse no arquivo de check-in e clique em **Check-in**.</span><span class="sxs-lookup"><span data-stu-id="d3570-109">In Solution Explorer, right-click the file to check in, and then click **Check In**.</span></span>  
  
2.  <span data-ttu-id="d3570-110">Se a caixa de diálogo **Check-in** for exibida, selecione as opções apropriadas e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3570-110">If the **Check In** dialog box appears, select the appropriate options, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d3570-111">**Fazer Check-in**</span><span class="sxs-lookup"><span data-stu-id="d3570-111">**Check In**</span></span>  
     <span data-ttu-id="d3570-112">Efetua check-in de todos os itens selecionados.</span><span class="sxs-lookup"><span data-stu-id="d3570-112">Check in all the selected items.</span></span>  
  
     <span data-ttu-id="d3570-113">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d3570-113">**Columns**</span></span>  
     <span data-ttu-id="d3570-114">Identifique as colunas a serem exibidas e a ordem em que elas são exibidas.</span><span class="sxs-lookup"><span data-stu-id="d3570-114">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="d3570-115">**Comentários**</span><span class="sxs-lookup"><span data-stu-id="d3570-115">**Comments**</span></span>  
     <span data-ttu-id="d3570-116">Adiciona um comentário a associar com a operação de check-in.</span><span class="sxs-lookup"><span data-stu-id="d3570-116">Add a comment to associate with the check-in operation.</span></span>  
  
     <span data-ttu-id="d3570-117">**Não mostrar caixa de diálogo Fazer Check-in ao fazer check-in dos itens**</span><span class="sxs-lookup"><span data-stu-id="d3570-117">**Don't show Check in dialog box when checking in items**</span></span>  
     <span data-ttu-id="d3570-118">Suprime a caixa de diálogo durante operações de check-in.</span><span class="sxs-lookup"><span data-stu-id="d3570-118">Suppress the dialog box during check-in operations.</span></span>  
  
     <span data-ttu-id="d3570-119">**Exibição Simples**</span><span class="sxs-lookup"><span data-stu-id="d3570-119">**Flat View**</span></span>  
     <span data-ttu-id="d3570-120">Exibe os arquivos dos quais está fazendo check-in como listas simples na conexão de controle do código fonte.</span><span class="sxs-lookup"><span data-stu-id="d3570-120">Display the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="d3570-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d3570-121">**Name**</span></span>  
     <span data-ttu-id="d3570-122">Exibe os nomes dos itens dos quais fazer check-in.</span><span class="sxs-lookup"><span data-stu-id="d3570-122">Displays the names of the items to check in.</span></span> <span data-ttu-id="d3570-123">Os itens aparecem com as caixas de seleção próximas a eles selecionadas.</span><span class="sxs-lookup"><span data-stu-id="d3570-123">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="d3570-124">Se não quiser fazer check-in de um item em particular, desmarque sua caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="d3570-124">If you do not want to check in a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="d3570-125">**Opções**</span><span class="sxs-lookup"><span data-stu-id="d3570-125">**Options**</span></span>  
     <span data-ttu-id="d3570-126">Exibe opções de check-in específico de plug-ins de controle do código fonte quando se clica na seta à direita do botão.</span><span class="sxs-lookup"><span data-stu-id="d3570-126">Displays source control plug-in-specific check-in options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="d3570-127">**Sort**</span><span class="sxs-lookup"><span data-stu-id="d3570-127">**Sort**</span></span>  
     <span data-ttu-id="d3570-128">Classifica a ordem das colunas exibidas.</span><span class="sxs-lookup"><span data-stu-id="d3570-128">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="d3570-129">**Exibição de árvore**</span><span class="sxs-lookup"><span data-stu-id="d3570-129">**Tree View**</span></span>  
     <span data-ttu-id="d3570-130">Exibe a hierarquia de pastas e arquivos dos itens dos quais está fazendo check-in.</span><span class="sxs-lookup"><span data-stu-id="d3570-130">Display the folder and file hierarchy for the items you are checking in.</span></span>  
  
 <span data-ttu-id="d3570-131">Se o arquivo com check-in não fizer parte de uma saída compartilhada, o ambiente do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] fará imediatamente o check-in do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3570-131">If the file you have checked in is not part of a shared checkout, the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment checks in the file immediately.</span></span> <span data-ttu-id="d3570-132">Caso contrário, você pode ser solicitado a mesclar sua versão com versões criadas por outros usuários.</span><span class="sxs-lookup"><span data-stu-id="d3570-132">Otherwise, it may prompt you to merge your version with versions created by other users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3570-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d3570-133">See Also</span></span>  
 <span data-ttu-id="d3570-134">[Exibir uma lista de arquivos modificados](../../2014/database-engine/view-a-list-of-modified-files.md) </span><span class="sxs-lookup"><span data-stu-id="d3570-134">[View a List of Modified Files](../../2014/database-engine/view-a-list-of-modified-files.md) </span></span>  
 [<span data-ttu-id="d3570-135">Gerenciar check-ins</span><span class="sxs-lookup"><span data-stu-id="d3570-135">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)  
  
  
