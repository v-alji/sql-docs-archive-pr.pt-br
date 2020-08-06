---
title: Caixa de diálogo opções de Construtor de Relatórios, configurações (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10427"
ms.assetid: 423360de-9bed-462e-921f-60a5abab004f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 07bd4a7f9dfe1abd8ab76765cb1ac10ff5227066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571322"
---
# <a name="report-builder-options-dialog-box-settings-report-builder"></a><span data-ttu-id="31f1e-102">Caixa de diálogo Opções do Construtor de Relatórios, Configurações (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="31f1e-102">Report Builder Options Dialog Box, Settings (Report Builder)</span></span>
  <span data-ttu-id="31f1e-103">Clique no botão **Construtor de relatórios** e, em seguida, clique em **Opções** para definir opções para mostrar os arquivos e as conexões recentes.</span><span class="sxs-lookup"><span data-stu-id="31f1e-103">Click the **Report Builder** button and then click **Options** to set options for showing recent files and connections.</span></span> <span data-ttu-id="31f1e-104">Também é possível alterar o servidor de relatório padrão ou adicionar um se você não tiver um padrão.</span><span class="sxs-lookup"><span data-stu-id="31f1e-104">You can also change the default report server, or add one if you don't have a default.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="31f1e-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="31f1e-105">UI element list</span></span>  
 <span data-ttu-id="31f1e-106">**Usar este servidor de relatório ou site do SharePoint por padrão**</span><span class="sxs-lookup"><span data-stu-id="31f1e-106">**Use this report server or SharePoint site by default**</span></span>  
 <span data-ttu-id="31f1e-107">Pode ser que o administrador tenha configurado essa opção.</span><span class="sxs-lookup"><span data-stu-id="31f1e-107">Your administrator may have configured this.</span></span> <span data-ttu-id="31f1e-108">O valor pode ser uma URL bem formada que inicia com http:// ou https://.</span><span class="sxs-lookup"><span data-stu-id="31f1e-108">The value can be a well-formed URL starting with http:// or https://.</span></span> <span data-ttu-id="31f1e-109">Essa configuração determina quais conexões da fonte de dados aparecem por padrão nos assistentes de Tabela/Matriz e de Gráfico.</span><span class="sxs-lookup"><span data-stu-id="31f1e-109">This setting determines which data source connections appear by default in the Table/Matrix and Chart wizards.</span></span> <span data-ttu-id="31f1e-110">Além disso, seus relatórios serão processados neste servidor e você poderá referenciar recursos deste servidor.</span><span class="sxs-lookup"><span data-stu-id="31f1e-110">In addition, your reports will be processed on this server and you can reference resources from this server.</span></span>  
  
 <span data-ttu-id="31f1e-111">Se você selecionar um servidor de relatório diferente, talvez seja necessário reiniciar o Construtor de Relatórios para que essa alteração tenha efeito.</span><span class="sxs-lookup"><span data-stu-id="31f1e-111">If you select a different report server, you may need to restart Report Builder in order for this change to take affect.</span></span>  
  
 <span data-ttu-id="31f1e-112">**Publicar partes de relatórios para esta pasta por padrão**</span><span class="sxs-lookup"><span data-stu-id="31f1e-112">**Publish report parts to this folder by default**</span></span>  
 <span data-ttu-id="31f1e-113">O Construtor de Relatórios salvará as partes do relatório que você publicar nesta pasta.</span><span class="sxs-lookup"><span data-stu-id="31f1e-113">Report Builder will save report parts that you publish to this folder.</span></span> <span data-ttu-id="31f1e-114">Se a pasta ainda não existir e você tiver permissões para criar pastas no servidor de relatório, o Construtor de Relatórios criará essa pasta.</span><span class="sxs-lookup"><span data-stu-id="31f1e-114">If the folder does not exist yet and you have permissions to create folders on the report server, Report Builder will create this folder.</span></span>  
  
 <span data-ttu-id="31f1e-115">Você não precisa reiniciar o Construtor de Relatórios para que essa configuração tenha efeito.</span><span class="sxs-lookup"><span data-stu-id="31f1e-115">You do not need to restart Report Builder for this setting to take effect.</span></span>  
  
 <span data-ttu-id="31f1e-116">**Mostrar este número de sites e servidores recentes**</span><span class="sxs-lookup"><span data-stu-id="31f1e-116">**Show this number of recent sites and servers**</span></span>  
 <span data-ttu-id="31f1e-117">Especifica o número de sites e conexões recentes a serem mostrados nas caixas de diálogo **Abrir Relatório** e **Salvar como Relatório** .</span><span class="sxs-lookup"><span data-stu-id="31f1e-117">Specify the number of recent sites and connections to show in the **Open Report** and **Save As Report** dialog boxes.</span></span>  
  
 <span data-ttu-id="31f1e-118">**Mostrar este número de conjuntos de dados compartilhados e conexões da fonte de dados compartilhadas recentes**</span><span class="sxs-lookup"><span data-stu-id="31f1e-118">**Show this number of recent shared datasets and data source connections**</span></span>  
 <span data-ttu-id="31f1e-119">Especifica o número de conjuntos de dados compartilhados e conexões de fonte de dados recentes a serem mostrados na caixa de diálogo **Propriedades do Conjunto de dados** e na página **Escolher uma conexão com uma fonte de dados** do Assistente de Regiões de Dados.</span><span class="sxs-lookup"><span data-stu-id="31f1e-119">Specify the number of recent shared datasets and data source connections to show in the **Dataset Properties** dialog box and the **Choose a connection to a data source** page of the Data Regions Wizard.</span></span>  
  
 <span data-ttu-id="31f1e-120">**Mostrar este número de documentos recentes**</span><span class="sxs-lookup"><span data-stu-id="31f1e-120">**Show this number of recent documents**</span></span>  
 <span data-ttu-id="31f1e-121">Especifica o número de documentos recentes a serem mostrados quando você clicar no botão Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="31f1e-121">Specify the number of recent documents to show when you click the Report Builder button.</span></span>  
  
 <span data-ttu-id="31f1e-122">**Limpar todas as listas de itens recentes**</span><span class="sxs-lookup"><span data-stu-id="31f1e-122">**Clear all recent item lists**</span></span>  
 <span data-ttu-id="31f1e-123">Limpa as listas atuais de sites e servidores recentes, bancos de dados compartilhados, conexões da fontes de dados compartilhadas e documentos.</span><span class="sxs-lookup"><span data-stu-id="31f1e-123">Clear the current lists of recent sites and servers, shared datasets, shared data source connections, and documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f1e-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31f1e-124">See Also</span></span>  
 [<span data-ttu-id="31f1e-125">Ajuda do Construtor de Relatórios para caixas de diálogo, painéis e assistentes</span><span class="sxs-lookup"><span data-stu-id="31f1e-125">Report Builder Help for Dialog Boxes, Panes, and Wizards</span></span>](../report-builder-help-for-dialog-boxes-panes-and-wizards.md)  
  
  
