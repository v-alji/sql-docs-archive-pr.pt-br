---
title: Editor do Gerenciador de conexões do Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelconnection.f1
helpviewer_keywords:
- Excel Connection Manager Editor
ms.assetid: 7ff097e4-cafb-4885-a898-05b2a46628c1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f66de13b710e5ccb577e6f2d67c215572e34767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574805"
---
# <a name="excel-connection-manager-editor"></a><span data-ttu-id="710fb-102">Editor de Gerenciador de Conexões Excel</span><span class="sxs-lookup"><span data-stu-id="710fb-102">Excel Connection Manager Editor</span></span>
  <span data-ttu-id="710fb-103">Use a caixa de diálogo **Editor de Gerenciador de Conexões Excel** para adicionar uma conexão a um arquivo da pasta de trabalho novo ou existente do [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="710fb-103">Use the **Excel Connection Manager Editor** dialog box to add a connection to an existing or a new [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook file.</span></span>  
  
 <span data-ttu-id="710fb-104">Para saber mais sobre o Gerenciador de Conexões Excel, consulte [Gerenciador de conexões do Excel](connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="710fb-104">To learn more about the Excel connection manager, see [Excel Connection Manager](connection-manager/excel-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="710fb-105">Não é possível estabelecer conexão com um arquivo do Excel protegido por senha.</span><span class="sxs-lookup"><span data-stu-id="710fb-105">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="options"></a><span data-ttu-id="710fb-106">Opções</span><span class="sxs-lookup"><span data-stu-id="710fb-106">Options</span></span>  
 <span data-ttu-id="710fb-107">**Caminho de arquivo do Excel**</span><span class="sxs-lookup"><span data-stu-id="710fb-107">**Excel file path**</span></span>  
 <span data-ttu-id="710fb-108">Digite o caminho e nome de arquivo de um arquivo de pasta de trabalho do Excel (.xls) novo ou existente.</span><span class="sxs-lookup"><span data-stu-id="710fb-108">Type the path and file name of an existing or a new Excel workbook file (.xls).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="710fb-109">O **Editor de destino do Excel** cria automaticamente o arquivo do Excel quando você seleciona uma **conexão do Excel** que aponta para um arquivo novo/não existente e, em seguida, clica em **novo** para **o nome da planilha do Excel**.</span><span class="sxs-lookup"><span data-stu-id="710fb-109">The **Excel Destination Editor** automatically creates the Excel file when you select an **Excel Connection** that points to a new/non-existent file and then click **New** for **Name of the Excel Sheet**.</span></span>  
  
 <span data-ttu-id="710fb-110">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="710fb-110">**Browse**</span></span>  
 <span data-ttu-id="710fb-111">Use a caixa de diálogo **abrir** para navegar até a pasta na qual o arquivo do Excel existe ou onde você deseja criar o novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="710fb-111">Use the **Open** dialog box to navigate to the folder in which the excel file exists or where you want to create the new file.</span></span>  
  
 <span data-ttu-id="710fb-112">**Versão do Excel**</span><span class="sxs-lookup"><span data-stu-id="710fb-112">**Excel version**</span></span>  
 <span data-ttu-id="710fb-113">Especifique a versão do Microsoft Excel que foi usada para criar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="710fb-113">Specify the version of Microsoft Excel that was used to create the file.</span></span>  
  
|<span data-ttu-id="710fb-114">Opção</span><span class="sxs-lookup"><span data-stu-id="710fb-114">Option</span></span>|<span data-ttu-id="710fb-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="710fb-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="710fb-116">Excel 97-2003</span><span class="sxs-lookup"><span data-stu-id="710fb-116">Excel 97-2003</span></span>|<span data-ttu-id="710fb-117">O arquivo foi criado usando o Excel 97 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="710fb-117">File was created using Excel 97 or later.</span></span>|  
|<span data-ttu-id="710fb-118">Excel 3,0</span><span class="sxs-lookup"><span data-stu-id="710fb-118">Excel 3.0</span></span>|<span data-ttu-id="710fb-119">O arquivo foi criado usando o Excel 3,0.</span><span class="sxs-lookup"><span data-stu-id="710fb-119">File was created using Excel 3.0.</span></span>|  
|<span data-ttu-id="710fb-120">Excel 4,0</span><span class="sxs-lookup"><span data-stu-id="710fb-120">Excel 4.0</span></span>|<span data-ttu-id="710fb-121">O arquivo foi criado usando o Excel 4.0.</span><span class="sxs-lookup"><span data-stu-id="710fb-121">File was created using Excel 4.0.</span></span>|  
|<span data-ttu-id="710fb-122">Excel 5,0</span><span class="sxs-lookup"><span data-stu-id="710fb-122">Excel 5.0</span></span>|<span data-ttu-id="710fb-123">O arquivo foi criado usando o Excel 95 (7.0).</span><span class="sxs-lookup"><span data-stu-id="710fb-123">File was created using Excel 95 (7.0).</span></span>|  
  
 <span data-ttu-id="710fb-124">**A primeira linha tem nomes de coluna**</span><span class="sxs-lookup"><span data-stu-id="710fb-124">**First row has column names**</span></span>  
 <span data-ttu-id="710fb-125">Especifique se a primeira linha de dados na planilha selecionada contém os nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="710fb-125">Specify whether the first row of data in the selected worksheet contains column names.</span></span> <span data-ttu-id="710fb-126">O valor padrão desta opção é **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="710fb-126">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="710fb-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="710fb-127">See Also</span></span>  
 <span data-ttu-id="710fb-128">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="710fb-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="710fb-129">Loop através de arquivos e tabelas do Excel por meio de um contêiner do Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="710fb-129">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
