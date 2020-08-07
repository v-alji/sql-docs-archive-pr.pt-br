---
title: Propriedades do servidor (página Histórico) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.history.f1
ms.assetid: be9d8018-a46f-4625-9ae1-138ebe6b38ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: df5ff9dc7a94431f8feec112d460938aa1631ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575014"
---
# <a name="server-properties-history-page"></a><span data-ttu-id="5d62a-102">Propriedades do Servidor (página Histórico)</span><span class="sxs-lookup"><span data-stu-id="5d62a-102">Server Properties (History Page)</span></span>
  <span data-ttu-id="5d62a-103">Use essa página para definir um valor padrão para o número de cópias do histórico de relatório a serem retidas.</span><span class="sxs-lookup"><span data-stu-id="5d62a-103">Use this page to set a default value for the number of copies of report history to retain.</span></span> <span data-ttu-id="5d62a-104">O valor padrão fornece uma configuração inicial que estabelece limites de histórico de relatório para todos os relatórios.</span><span class="sxs-lookup"><span data-stu-id="5d62a-104">The default value provides an initial setting that establishes report history limits for all reports.</span></span> <span data-ttu-id="5d62a-105">Você pode variar essas configurações para relatórios individuais.</span><span class="sxs-lookup"><span data-stu-id="5d62a-105">You can vary these settings for individual reports.</span></span>  
  
 <span data-ttu-id="5d62a-106">Histórico de relatório é uma coleção de instantâneos de relatórios que inclui dados do relatório e o layout atual do relatório no momento em que o instantâneo foi criado.</span><span class="sxs-lookup"><span data-stu-id="5d62a-106">Report history is a collection of report snapshots that include report data and layout that is current for the report at the time the snapshot is created.</span></span> <span data-ttu-id="5d62a-107">Você pode usar o histórico de relatórios para manter uma cópia de um relatório como ele era em uma data e hora específica.</span><span class="sxs-lookup"><span data-stu-id="5d62a-107">You can use report history to keep a copy of a report as it was on a specific date or time.</span></span> <span data-ttu-id="5d62a-108">Você pode criar e gerenciar histórico de relatório para relatórios individuais executados em um servidor de relatório no modo nativo ou um servidor de relatório configurado para o modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5d62a-108">You can create and manage report history for individual reports that run on a native mode report server or a report server that is configured for SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="5d62a-109">Instantâneos de relatórios são armazenados no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5d62a-109">Report history snapshots are stored in the report server database.</span></span> <span data-ttu-id="5d62a-110">Se você mantém um número ilimitado de instantâneos, verifique periodicamente o tamanho do banco de dados para se certificar de que ele não esteja crescendo com muita rapidez ou consumindo muito espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="5d62a-110">If you keep an unlimited number of snapshots, be sure to periodically check the database size to ensure it is not growing too fast or consuming too much disk space.</span></span>  
  
 <span data-ttu-id="5d62a-111">Para abrir essa página, inicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se a uma instância de servidor de relatórios, clique com o botão direito do mouse no nome do servidor de relatórios e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5d62a-111">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="5d62a-112">Clique em **Histórico** para abrir essa página.</span><span class="sxs-lookup"><span data-stu-id="5d62a-112">Click **History** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5d62a-113">Opções</span><span class="sxs-lookup"><span data-stu-id="5d62a-113">Options</span></span>  
 <span data-ttu-id="5d62a-114">**Manter um número ilimitado de instantâneos no histórico de relatório**</span><span class="sxs-lookup"><span data-stu-id="5d62a-114">**Keep an unlimited number of snapshots in report history**</span></span>  
 <span data-ttu-id="5d62a-115">Retenha todos os instantâneos de histórico de relatório.</span><span class="sxs-lookup"><span data-stu-id="5d62a-115">Retain all report history snapshots.</span></span> <span data-ttu-id="5d62a-116">Você deve excluir instantâneos manualmente para reduzir o tamanho de histórico de relatórios.</span><span class="sxs-lookup"><span data-stu-id="5d62a-116">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
 <span data-ttu-id="5d62a-117">**Limitar as cópias do histórico de relatório**</span><span class="sxs-lookup"><span data-stu-id="5d62a-117">**Limit the copies of report history**</span></span>  
 <span data-ttu-id="5d62a-118">Retenha um número de conjunto de instantâneos de histórico de relatório.</span><span class="sxs-lookup"><span data-stu-id="5d62a-118">Retain a set number of report history snapshots.</span></span> <span data-ttu-id="5d62a-119">Quando o limite é alcançado, cópias mais antigas são removidas do histórico do relatório para liberar espaço para cópias mais atuais.</span><span class="sxs-lookup"><span data-stu-id="5d62a-119">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="5d62a-120">Se, posteriormente, você limitar o histórico de relatório, quando o histórico existente exceder o limite especificado, o servidor de relatório reduzirá o histórico existente ao novo limite.</span><span class="sxs-lookup"><span data-stu-id="5d62a-120">If you limit report history later, when the existing report history exceeds the limit you specify, the report server reduces the existing report history to the new limit.</span></span> <span data-ttu-id="5d62a-121">Os instantâneos de relatórios mais antigos são excluídos primeiro.</span><span class="sxs-lookup"><span data-stu-id="5d62a-121">The oldest report snapshots are deleted first.</span></span> <span data-ttu-id="5d62a-122">Se o histórico de relatórios estiver vazio ou abaixo do limite, novos instantâneos de relatório serão adicionados.</span><span class="sxs-lookup"><span data-stu-id="5d62a-122">If report history is empty or below the limit, new report snapshots are added.</span></span> <span data-ttu-id="5d62a-123">Quando o limite é alcançado, o instantâneo mais antigo é excluído e um novo instantâneo de relatório é adicionado.</span><span class="sxs-lookup"><span data-stu-id="5d62a-123">When the limit is reached, the oldest snapshot is deleted when a new report snapshot is added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d62a-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5d62a-124">See Also</span></span>  
 <span data-ttu-id="5d62a-125">[Definir propriedades do servidor de relatório &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="5d62a-125">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="5d62a-126">[Conectar-se a um servidor de relatório no Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="5d62a-126">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="5d62a-127">Servidor de Relatório na ajuda F1 do Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d62a-127">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
