---
title: Cancelar supressão da execução de avisos de relatório personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 0deed900-c910-4d12-aac0-6ab9e39eb068
author: stevestein
ms.author: sstein
ms.openlocfilehash: 725362ff7f8a6c282529f652e8813a8083257eb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678544"
---
# <a name="unsuppress-run-custom-report-warnings"></a><span data-ttu-id="b051c-102">Cancelar supressão da execução de avisos de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="b051c-102">Unsuppress Run Custom Report Warnings</span></span>
  <span data-ttu-id="b051c-103">Há duas caixas de diálogo de aviso para relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="b051c-103">There are two warning dialog boxes for custom reports.</span></span> <span data-ttu-id="b051c-104">Este tópico descreve como cancelar a supressão da exibição dessas caixas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b051c-104">This topic describes how to unsuppress the display of these boxes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b051c-105">Por padrão, a caixa de diálogo **Executar Relatórios Personalizados** aparece antes da execução de um relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="b051c-105">By default, the **Run Custom Reports** dialog box appears before a custom report runs.</span></span> <span data-ttu-id="b051c-106">Se você marcar a caixa de seleção **Não mostrar este aviso novamente** , a caixa de diálogo não aparecerá mais.</span><span class="sxs-lookup"><span data-stu-id="b051c-106">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span> <span data-ttu-id="b051c-107">Além disso, por padrão, a caixa de diálogo **Executar Relatórios Personalizados** aparece quando você abre um relatório personalizado e, em seguida, clica em um link para abrir outro relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="b051c-107">Also by default, the **Run Custom Reports** dialog box appears when you open a custom report and then click a link to open another custom report.</span></span> <span data-ttu-id="b051c-108">Essa caixa de diálogo exibe o caminho de preenchimento para o arquivo de relatório detalhado personalizado.</span><span class="sxs-lookup"><span data-stu-id="b051c-108">This dialog box displays the fill path to the drill-through custom report file.</span></span> <span data-ttu-id="b051c-109">Se você marcar a caixa de seleção **Não mostrar este aviso novamente** , a caixa de diálogo não aparecerá mais.</span><span class="sxs-lookup"><span data-stu-id="b051c-109">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b051c-110">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b051c-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-unsuppress-the-main-custom-report-warning-dialog-box"></a><span data-ttu-id="b051c-111">Para cancelar a supressão da caixa de diálogo de aviso do relatório personalizado principal</span><span class="sxs-lookup"><span data-stu-id="b051c-111">To unsuppress the main custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="b051c-112">Conecte-se ao \<*Server*> \\ < *compartilhamento* >| \<*Drive*> \Documents and Settings \\<USERPROFILE \> \Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span><span class="sxs-lookup"><span data-stu-id="b051c-112">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="b051c-113">Clique com o botão direito do mouse em `reports.xml` e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b051c-113">Right-click `reports.xml`, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="b051c-114">Altere\*\* \<SuppressWarning> true \</SuppressWarning> para \<SuppressWarning> false \</SuppressWarning> \*\*.</span><span class="sxs-lookup"><span data-stu-id="b051c-114">Change**\<SuppressWarning>true\</SuppressWarning> to \<SuppressWarning>false\</SuppressWarning>**.</span></span>  
  
4.  <span data-ttu-id="b051c-115">Reinicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b051c-115">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-unsuppress-the-drill-through-custom-report-warning-dialog-box"></a><span data-ttu-id="b051c-116">Para cancelar a supressão da caixa de diálogo de aviso do relatório detalhado personalizado</span><span class="sxs-lookup"><span data-stu-id="b051c-116">To unsuppress the drill-through custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="b051c-117">Conecte-se ao \<*Server*> \\ < *compartilhamento* >| \<*Drive*> \Documents and Settings \\<USERPROFILE \> \Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span><span class="sxs-lookup"><span data-stu-id="b051c-117">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="b051c-118">Clique com o botão direito do mouse `reports.xml` e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b051c-118">Right-click `reports.xml`, and click **Edit**.</span></span>  
  
3.  <span data-ttu-id="b051c-119">Altere \*\* \<SuppressDrillthroughWarning> true \</SuppressDrillthroughWarning> para \<SuppressDrillthroughWarning> false \</SuppressDrillthroughWarning> \*\*.</span><span class="sxs-lookup"><span data-stu-id="b051c-119">Change **\<SuppressDrillthroughWarning>true\</SuppressDrillthroughWarning>to \<SuppressDrillthroughWarning>false\</SuppressDrillthroughWarning>**.</span></span>  
  
4.  <span data-ttu-id="b051c-120">Reinicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b051c-120">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b051c-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b051c-121">See Also</span></span>  
 <span data-ttu-id="b051c-122">[Relatórios personalizados no Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b051c-122">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="b051c-123">[Adicionar um relatório personalizado a Management Studio](add-a-custom-report-to-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b051c-123">[Add a Custom Report to Management Studio](add-a-custom-report-to-management-studio.md) </span></span>  
 [<span data-ttu-id="b051c-124">Usar relatórios personalizados com propriedades de nó do Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="b051c-124">Use Custom Reports with Object Explorer Node Properties</span></span>](use-custom-reports-with-object-explorer-node-properties.md)  
  
  
