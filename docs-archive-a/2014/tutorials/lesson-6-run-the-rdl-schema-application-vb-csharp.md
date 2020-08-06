---
title: 'Lição 6: executar o aplicativo de esquema RDL (VB-C #) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2cd2386-2df8-4b69-ab81-9ad1a31f6d27
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 5a0fc2cd9c12b4b1602f517dc215ca44e686c663
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678361"
---
# <a name="lesson-6-run-the-rdl-schema-application-vb-c"></a><span data-ttu-id="7f99f-102">Lição 6: executar o aplicativo de esquema RDL (VB-C #)</span><span class="sxs-lookup"><span data-stu-id="7f99f-102">Lesson 6: Run the RDL Schema Application (VB-C#)</span></span>
  <span data-ttu-id="7f99f-103">O [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] oferece dois métodos para criar e executar um aplicativo de console com base no ambiente de desenvolvimento integrado (IDE):</span><span class="sxs-lookup"><span data-stu-id="7f99f-103">[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] offers two methods to build and run a console application from the integrated development environment (IDE):</span></span>  
  
-   <span data-ttu-id="7f99f-104">Iniciar (com Depuração)</span><span class="sxs-lookup"><span data-stu-id="7f99f-104">Start (with Debugging)</span></span>  
  
-   <span data-ttu-id="7f99f-105">Iniciar sem Depuração</span><span class="sxs-lookup"><span data-stu-id="7f99f-105">Start without Debugging</span></span>  
  
### <a name="to-build-and-run-the-samplerdlschema-application"></a><span data-ttu-id="7f99f-106">Criar e executar o aplicativo SampleRDLSchema</span><span class="sxs-lookup"><span data-stu-id="7f99f-106">To build and run the SampleRDLSchema application</span></span>  
  
1.  <span data-ttu-id="7f99f-107">No menu **Depuração**, clique em **Iniciar sem depuração**.</span><span class="sxs-lookup"><span data-stu-id="7f99f-107">From the **Debug** menu, click **Start Without Debugging**.</span></span> <span data-ttu-id="7f99f-108">Isso assegura que a janela de console permaneça aberta após o fim da execução do programa.</span><span class="sxs-lookup"><span data-stu-id="7f99f-108">This ensures that the console window remains open after the program has finished executing.</span></span>  
  
     <span data-ttu-id="7f99f-109">O aplicativo imprime a seguinte saída para o console:</span><span class="sxs-lookup"><span data-stu-id="7f99f-109">The application prints the following output to the console:</span></span>  
  
    ```  
    Loading Report Definition  
    Updating Report Definition  
    - Old Description: <Old Report Description>  
    - New Description: <New Report Description>  
    Publishing Report Definition  
    ```  
  
2.  <span data-ttu-id="7f99f-110">Pressione qualquer tecla para fechar o console.</span><span class="sxs-lookup"><span data-stu-id="7f99f-110">Press any key to close the console.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7f99f-111">Qualquer erro que ocorra será gravado no console.</span><span class="sxs-lookup"><span data-stu-id="7f99f-111">Any errors that occur are written to the console.</span></span>  
  
3.  <span data-ttu-id="7f99f-112">Quando a execução do aplicativo de exemplo terminar, uma cópia atualizada do relatório será salva no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="7f99f-112">When the sample application is finished running an updated copy of the report will be saved to the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f99f-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f99f-113">See Also</span></span>  
 <span data-ttu-id="7f99f-114">[Atualizando relatórios usando classes geradas do esquema RDL &#40;tutorial do SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="7f99f-114">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="7f99f-115">Linguagem RDL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7f99f-115">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
