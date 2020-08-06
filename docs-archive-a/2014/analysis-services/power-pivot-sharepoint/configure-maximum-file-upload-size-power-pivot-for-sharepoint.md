---
title: Configurar o tamanho máximo de upload de arquivo (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ac516c63-1e79-4ae8-bca6-32d3c1a09c00
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34a0adb2f22915289cccfa1f21c51038263acca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678305"
---
# <a name="configure-maximum-file-upload-size-powerpivot-for-sharepoint"></a><span data-ttu-id="66d28-102">Configurar o tamanho máximo do carregamento de arquivo (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="66d28-102">Configure Maximum File Upload Size (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="66d28-103">As pastas de trabalho PowerPivot geralmente contêm grandes quantidades de dados que resultam em arquivos que excedem o tamanho máximo de arquivo permitido para carregamentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="66d28-103">PowerPivot workbooks often contain large amounts of data that result in files that exceed the maximum file size allowed for SharePoint uploads.</span></span> <span data-ttu-id="66d28-104">Ao tentar carregar um arquivo que excede o limite superior, você receberá o seguinte erro no SharePoint:</span><span class="sxs-lookup"><span data-stu-id="66d28-104">When you try to upload a file that exceeds the upper limit, you will get the following error on SharePoint:</span></span>  
  
-   <span data-ttu-id="66d28-105">"O arquivo especificado é maior que o tamanho máximo de arquivo permitido".</span><span class="sxs-lookup"><span data-stu-id="66d28-105">"The specified file is larger than the maximum supported file size."</span></span>  
  
 <span data-ttu-id="66d28-106">Para aumentar o tamanho de arquivo, inicie ajustando o Tamanho Máximo da Pasta de Trabalho para Serviços do Excel para 50 megabytes.</span><span class="sxs-lookup"><span data-stu-id="66d28-106">To increase the file size, start by adjusting the Maximum Workbook Size for Excel Services to 50 megabytes.</span></span> <span data-ttu-id="66d28-107">Isso alinha os limites máximos de tamanho de arquivo para o Excel com os dos aplicativos Web do SharePoint (definidos para 50 megabytes por padrão no SharePoint 2010 e 200 no SharePoint 2013).</span><span class="sxs-lookup"><span data-stu-id="66d28-107">This aligns the maximum file size limits for Excel to those of SharePoint web applications (set to 50 megabytes by default in SharePoint 2010 and 200 in SharePoint 2013).</span></span> <span data-ttu-id="66d28-108">Se seus arquivos excederem 50 megabytes em tamanho, aumente os limites de tamanho de arquivo para Serviços do Excel e para o aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="66d28-108">If your files exceed 50 megabytes in size, increase the file size limits for both Excel Services and your web application.</span></span>  
  
 <span data-ttu-id="66d28-109">Você deve ser administrador do SharePoint para alterar o tamanho máximo de carregamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="66d28-109">You must be a SharePoint administrator to change the maximum file upload size.</span></span>  
  
### <a name="configure-maximum-file-size-for-excel-services"></a><span data-ttu-id="66d28-110">Configurar tamanho máximo de arquivo para Serviços do Excel</span><span class="sxs-lookup"><span data-stu-id="66d28-110">Configure maximum file size for Excel Services</span></span>  
  
1.  <span data-ttu-id="66d28-111">Na Administração Central, em Gerenciamento de Aplicativo, clique em **Gerenciar aplicativos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="66d28-111">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="66d28-112">Clique no nome do Aplicativo de Serviços do seu Excel.</span><span class="sxs-lookup"><span data-stu-id="66d28-112">Click the name of your Excel Services Application.</span></span>  
  
3.  <span data-ttu-id="66d28-113">Clique em **Locais de Arquivos Confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="66d28-113">Click **Trusted File Locations**.</span></span>  
  
4.  <span data-ttu-id="66d28-114">Clique no local para editar as propriedades.</span><span class="sxs-lookup"><span data-stu-id="66d28-114">Click the location to edit the properties.</span></span> <span data-ttu-id="66d28-115">Por padrão, os Serviços do Excel consideram o aplicativo Web padrão um site de confiança.</span><span class="sxs-lookup"><span data-stu-id="66d28-115">By default, Excel Services considers the default web application a trusted site.</span></span> <span data-ttu-id="66d28-116">Se você estiver usando o aplicativo Web padrão, clique em **http://** abrir a página de configuração para este local.</span><span class="sxs-lookup"><span data-stu-id="66d28-116">If you are using the default web application, click **http://** to open the configuration page for this location.</span></span>  
  
5.  <span data-ttu-id="66d28-117">Role para as **Propriedades da Pasta de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="66d28-117">Scroll to **Workbook Properties**.</span></span>  
  
6.  <span data-ttu-id="66d28-118">Em Tamanho Máximo da Pasta de Trabalho, aumente o tamanho do arquivo de 10 (o valor padrão) para 50 ou um tamanho maior que acomode os arquivos em você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="66d28-118">In Maximum Workbook Size, increase the file size from 10 (the default value) to 50 or a larger size that accommodates the files you are working with.</span></span>  
  
     <span data-ttu-id="66d28-119">Por padrão, 50 megabytes é o tamanho máximo de carregamento de arquivo para aplicativos Web do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="66d28-119">By default, 50 megabytes is the maximum file upload size for SharePoint web applications.</span></span> <span data-ttu-id="66d28-120">Se você definir Tamanho Máximo da Pasta de Trabalho como um número maior que 50 megabytes, siga as etapas no próximo procedimento para aumentar o Tamanho Máximo de Carregamento para o aplicativo Web do SharePoint para o mesmo valor.</span><span class="sxs-lookup"><span data-stu-id="66d28-120">If you set Maximum Workbook Size to a number larger than 50 megabytes, follow the steps in the next procedure to increase the Maximum Upload Size for your SharePoint web application to the same value.</span></span>  
  
     <span data-ttu-id="66d28-121">O valor máximo que você pode especificar é 2 gigabytes (ou 2047 megabytes como especificado na Administração Central).</span><span class="sxs-lookup"><span data-stu-id="66d28-121">The maximum value that you can specify is 2 gigabytes (or 2047 megabytes as specified in Central Administration).</span></span>  
  
7.  <span data-ttu-id="66d28-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="66d28-122">Click **OK**.</span></span>  
  
### <a name="configure-maximum-file-size-for-a-sharepoint-web-application"></a><span data-ttu-id="66d28-123">Configurar o tamanho máximo do arquivo para um aplicativo Web do SharePoint</span><span class="sxs-lookup"><span data-stu-id="66d28-123">Configure maximum file size for a SharePoint web application</span></span>  
  
1.  <span data-ttu-id="66d28-124">Na administração central, em gerenciamento de aplicativos, clique em **gerenciar aplicativos Web**.</span><span class="sxs-lookup"><span data-stu-id="66d28-124">In Central Administration, in Application Management, click **Manage web applications**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="66d28-125">Execute as etapas a seguir somente se você tiver aumentado o Tamanho Máximo da Pasta de Trabalho nos Serviços do Excel.</span><span class="sxs-lookup"><span data-stu-id="66d28-125">Perform the following steps only if you increased the Maximum Workbook Size in Excel Services.</span></span>  
  
2.  <span data-ttu-id="66d28-126">Selecione o aplicativo (por exemplo, **SharePoint - 80**).</span><span class="sxs-lookup"><span data-stu-id="66d28-126">Select the application (for example, **SharePoint - 80**).</span></span>  
  
3.  <span data-ttu-id="66d28-127">Na faixa de opções de Aplicativos Web, clique na seta para baixo no botão de Configurações Gerais.</span><span class="sxs-lookup"><span data-stu-id="66d28-127">On the Web Applications ribbon, click the down arrow on the General Settings button.</span></span>  
  
4.  <span data-ttu-id="66d28-128">Clique em **configurações gerais**.</span><span class="sxs-lookup"><span data-stu-id="66d28-128">Click **General Settings**.</span></span>  
  
5.  <span data-ttu-id="66d28-129">Role para **Tamanho Máximo do Carregamento**.</span><span class="sxs-lookup"><span data-stu-id="66d28-129">Scroll to **Maximum Upload Size**.</span></span>  
  
6.  <span data-ttu-id="66d28-130">Defina a propriedade com o mesmo número, ou maior, que o Tamanho Máximo da Pasta de Trabalho em Serviços do Excel.</span><span class="sxs-lookup"><span data-stu-id="66d28-130">Set the property to the same number, or larger as the Maximum Workbook Size in Excel Services.</span></span>  
  
7.  <span data-ttu-id="66d28-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="66d28-131">Click **OK**.</span></span>  
  
  
