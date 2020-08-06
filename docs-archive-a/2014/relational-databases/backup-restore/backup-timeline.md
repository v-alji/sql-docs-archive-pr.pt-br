---
title: Linha do tempo de backup | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.POINTINTIMERESTORE.F1
- sql12.swb.backuptimeline.f1
helpviewer_keywords:
- Backup Timeline
ms.assetid: ae3565f2-ddb2-4469-a992-7531d4f9ebb8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b075f8c9ec32cfe483c64e34e9f9b4e4b6e80e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583674"
---
# <a name="backup-timeline"></a><span data-ttu-id="67c02-102">Linha do tempo de backup</span><span class="sxs-lookup"><span data-stu-id="67c02-102">Backup Timeline</span></span>
  <span data-ttu-id="67c02-103">Use a caixa de diálogo **Linha do Tempo de Backup** para localizar e especificar backups para restaurar um banco de dados em um ponto específico.</span><span class="sxs-lookup"><span data-stu-id="67c02-103">Use the **Backup Timeline** dialog box to locate and specify backups to restore a database to a point-in-time.</span></span> <span data-ttu-id="67c02-104">Acesse a caixa de diálogo **Linha do Tempo de Backup** clicando em **Linha do Tempo** no painel **Restaurar Banco de dados (Página Geral)** .</span><span class="sxs-lookup"><span data-stu-id="67c02-104">The **Backup Timeline** dialog box is accessed by clicking **Timeline** on the **Restore Database (General Page)** pane.</span></span> <span data-ttu-id="67c02-105">Esta caixa de diálogo permite exibir uma linha do tempo das operações de restauração executadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="67c02-105">This dialog box allows you to view a timeline of the restore operations performed on the database.</span></span>  
  
 <span data-ttu-id="67c02-106">O orientador de recuperação de banco de dados garante que apenas os backups necessários para restaurar até o ponto especificado sejam selecionados.</span><span class="sxs-lookup"><span data-stu-id="67c02-106">The Database Recovery Advisor ensures that only backups that are required for restoring to that point in time are selected.</span></span> <span data-ttu-id="67c02-107">Esses backups selecionados compõem o plano de restauração recomendado para a operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="67c02-107">These selected backups make up the recommended restore plan for your restore operation.</span></span> <span data-ttu-id="67c02-108">Você deve usar apenas os backups selecionados.</span><span class="sxs-lookup"><span data-stu-id="67c02-108">You should use only the selected backups.</span></span> <span data-ttu-id="67c02-109">Para obter informações sobre o Orientador de Recuperação de Banco de Dados, confira [Visão geral da restauração e recuperação &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="67c02-109">For information about the Database Recovery Advisor, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
## <a name="restore-to"></a><span data-ttu-id="67c02-110">Restaurar para</span><span class="sxs-lookup"><span data-stu-id="67c02-110">Restore to</span></span>  
 <span data-ttu-id="67c02-111">**Último backup feito** está selecionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="67c02-111">**Last backup taken** is selected by default.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="67c02-112">selecionará os backups apropriados para restaurar o banco de dados, e restaurará o banco de dados para o ponto do último backup.</span><span class="sxs-lookup"><span data-stu-id="67c02-112">will select the appropriate backups to restore the database, and will restore the database to the point of the last backup.</span></span> <span data-ttu-id="67c02-113">Clique em **Data e hora específicas** para definir manualmente a data e a hora (selecionando um ponto específico no tempo).</span><span class="sxs-lookup"><span data-stu-id="67c02-113">Click **A specific date and time** to manually set the date and time (selecting a specific point in time).</span></span>  
  
 <span data-ttu-id="67c02-114">**Data e hora específicas** permite que você pare a restauração a uma data e hora especificadas por você.</span><span class="sxs-lookup"><span data-stu-id="67c02-114">**Specific date and time** permits you stop the restore at a specific date and time that you select.</span></span> <span data-ttu-id="67c02-115">A linha de tempo mostra uma representação das operações de backup executadas 24 horas ma seleção de data e hora.</span><span class="sxs-lookup"><span data-stu-id="67c02-115">The timeline shows a representation of the backup operations performed in the 24 hours around the select date and time.</span></span>  
  
 <span data-ttu-id="67c02-116">**Data**</span><span class="sxs-lookup"><span data-stu-id="67c02-116">**Date**</span></span>  
 <span data-ttu-id="67c02-117">Insira ou selecione uma data na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="67c02-117">Enter or select a date from the drop-down list.</span></span>  
  
 <span data-ttu-id="67c02-118">**Hora**</span><span class="sxs-lookup"><span data-stu-id="67c02-118">**Time**</span></span>  
 <span data-ttu-id="67c02-119">Insira ou selecione uma data para designar o ponto específico no tempo para a restauração parar.</span><span class="sxs-lookup"><span data-stu-id="67c02-119">Enter or select a date to designate the specific point-in-time for the restore to stop.</span></span>  
  
 <span data-ttu-id="67c02-120">**Intervalo na linha de tempo**</span><span class="sxs-lookup"><span data-stu-id="67c02-120">**Timeline Interval**</span></span>  
 <span data-ttu-id="67c02-121">Exibe as opções para os tipos de intervalo que podem ser exibidos na linha do tempo.</span><span class="sxs-lookup"><span data-stu-id="67c02-121">Displays the options for the interval types viewable on the timeline.</span></span>  
  
## <a name="timeline-and-legend"></a><span data-ttu-id="67c02-122">Linha de tempo e legenda</span><span class="sxs-lookup"><span data-stu-id="67c02-122">Timeline and Legend</span></span>  
 <span data-ttu-id="67c02-123">Use a barra de rolagem abaixo da linha do tempo para mover o cursor para a frente e para trás ao longo da linha do tempo.</span><span class="sxs-lookup"><span data-stu-id="67c02-123">Use the scroll bar beneath the timeline to move the cursor forward and backward along the timeline.</span></span> <span data-ttu-id="67c02-124">Clique em um backup para mover a barra de rolagem ao término desse backup.</span><span class="sxs-lookup"><span data-stu-id="67c02-124">Click on a backup to move the scroll bar to the end of that backup.</span></span> <span data-ttu-id="67c02-125">Mova o mouse sobre um marcador para exibir uma Dica de tela que fornece informações sobre o conjunto de backup selecionado.</span><span class="sxs-lookup"><span data-stu-id="67c02-125">Hover the mouse over a marker to display a ScreenTip providing information about the selected backup set.</span></span> <span data-ttu-id="67c02-126">As informações de backup são mostradas na linha do tempo pelos marcadores a seguir.</span><span class="sxs-lookup"><span data-stu-id="67c02-126">Backup information is shown on the timeline by the following markers.</span></span>  
  
 <span data-ttu-id="67c02-127">Triângulo maior</span><span class="sxs-lookup"><span data-stu-id="67c02-127">Larger triangle</span></span>  
 <span data-ttu-id="67c02-128">Representa os backups completos executados no banco de dados, denotando o ponto específico no tempo em que cada backup completo foi executado.</span><span class="sxs-lookup"><span data-stu-id="67c02-128">Represents the full backups performed on the database, denoting the specific point in time each full backup was performed.</span></span>  
  
 <span data-ttu-id="67c02-129">Triângulo menor</span><span class="sxs-lookup"><span data-stu-id="67c02-129">Smaller triangle</span></span>  
 <span data-ttu-id="67c02-130">Representa os backups diferenciais executados no banco de dados, denotando o ponto específico no tempo em que cada backup diferencial foi executado.</span><span class="sxs-lookup"><span data-stu-id="67c02-130">Represents the differential backups performed on the database, denoting the specific point in time that each differential backup was performed.</span></span>  
  
 <span data-ttu-id="67c02-131">Áreas sombreadas verdes</span><span class="sxs-lookup"><span data-stu-id="67c02-131">Green shaded areas</span></span>  
 <span data-ttu-id="67c02-132">Representa a cobertura de backup do log de transações.</span><span class="sxs-lookup"><span data-stu-id="67c02-132">Represents the transaction log backup coverage.</span></span>  
  
 <span data-ttu-id="67c02-133">Linha vermelha</span><span class="sxs-lookup"><span data-stu-id="67c02-133">Red line</span></span>  
 <span data-ttu-id="67c02-134">Pode ser posicionada somente ao longo da linha do tempo onde a restauração é possível.</span><span class="sxs-lookup"><span data-stu-id="67c02-134">Can only be positioned along the timeline where the restore is possible.</span></span> <span data-ttu-id="67c02-135">A movimentação da linha vermelha ao longo da linha do tempo ajusta a data e a hora exibidas nas caixas **Data** e **Hora** .</span><span class="sxs-lookup"><span data-stu-id="67c02-135">Moving the red line along the timeline adjusts the date and time displayed in the **Date** and **Time** boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c02-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67c02-136">See Also</span></span>  
 [<span data-ttu-id="67c02-137">Restaurar banco de dados &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="67c02-137">Restore Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
  
