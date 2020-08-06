---
title: Depurando procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- debugging stored procedures [Analysis Services]
- stored procedures [Analysis Services], debugging
ms.assetid: 34f51b85-02b3-40dd-bf93-375a9e522385
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4f5971fe611f06a413ca48b2bc91237a8c87ee8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680697"
---
# <a name="debugging-stored-procedures"></a><span data-ttu-id="ec7dc-102">Depurando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="ec7dc-102">Debugging Stored Procedures</span></span>
  <span data-ttu-id="ec7dc-103">Os procedimentos armazenados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] são, na verdade, bibliotecas CLR ou COM (normalmente DLLs) escritas em C# (ou em outra linguagem CLR ou COM).</span><span class="sxs-lookup"><span data-stu-id="ec7dc-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures are actually CLR or COM libraries (normally DLLs) that are written in C# (or any other CLR or COM language).</span></span> <span data-ttu-id="ec7dc-104">Portanto, depurar um procedimento armazenado é bem parecido com depurar outro aplicativo no ambiente de depuração do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-104">Therefore, debugging a stored procedure is much like debugging any other application in the Visual Studio debugging environment.</span></span> <span data-ttu-id="ec7dc-105">Você depura procedimentos armazenados no ambiente de desenvolvimento do Visual Studio usando funções de depuração integradas.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-105">You debug stored procedures in the Visual Studio development environment using the integrated debugging functions.</span></span> <span data-ttu-id="ec7dc-106">Elas permitem que você pare nas localizações do procedimento, verifique a memória e os valores do Registro, altere variáveis, observe o tráfego de mensagens e analise como o código funciona.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-106">These allow you to stop at procedure locations, inspect memory and register values, change variables, observe message traffic and get a close look at how your code works.</span></span>  
  
### <a name="to-debug-a-stored-procedure"></a><span data-ttu-id="ec7dc-107">Depurar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="ec7dc-107">To debug a stored procedure</span></span>  
  
1.  <span data-ttu-id="ec7dc-108">Abra o projeto usado para criar a DLL no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-108">Open the project used to create the DLL in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="ec7dc-109">Crie pontos de interrupção no método ou na função correspondente ao procedimento que você deseja depurar.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-109">Create breakpoints in the method or function corresponding to the procedure you want to debug.</span></span>  
  
3.  <span data-ttu-id="ec7dc-110">Use o Visual Studio para criar uma compilação para depuração de uma DLL de procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-110">Use Visual Studio to create a debug build of a stored procedure DLL.</span></span>  
  
4.  <span data-ttu-id="ec7dc-111">Implante a DLL no servidor.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-111">Deploy the DLL to the server.</span></span> <span data-ttu-id="ec7dc-112">Para obter mais informações sobre como implantar a DLL no servidor, consulte [criando procedimentos armazenados](creating-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ec7dc-112">For more information about deploying the DLL to the server, see [Creating Stored Procedures](creating-stored-procedures.md).</span></span>  
  
5.  <span data-ttu-id="ec7dc-113">Você precisa de um aplicativo que chame o procedimento armazenado que deseja testar.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-113">You need an application that calls the stored procedure that you want to test.</span></span> <span data-ttu-id="ec7dc-114">Se ainda não houver um aplicativo pronto, use o Editor de Consultas MDX do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para criar uma consulta MDX para chamar o procedimento armazenado que será testado.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-114">If you do not have one ready, you can use the MDX Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create an MDX query that calls the stored procedure that you want to test.</span></span>  
  
6.  <span data-ttu-id="ec7dc-115">No Visual Studio, anexe ao processo do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (Msmdsrv.exe).</span><span class="sxs-lookup"><span data-stu-id="ec7dc-115">In Visual Studio, attach to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process (Msmdsrv.exe).</span></span>  
  
    1.  <span data-ttu-id="ec7dc-116">No menu **depurar** , escolha **attatch toprocess**.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-116">From the **Debug** menu, choose **Attatch toProcess**.</span></span>  
  
    2.  <span data-ttu-id="ec7dc-117">Na caixa de diálogo **attatch toprocess** , selecione **Mostrar processos de todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-117">In the **Attatch toProcess** dialog box, select **Show processes from all users**.</span></span>  
  
    3.  <span data-ttu-id="ec7dc-118">Na lista **processos disponíveis** , na coluna **processo** , clique em **Msmdsrv.exe**.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-118">In the **Available Processes** list, in the **Process** column, click **Msmdsrv.exe**.</span></span> <span data-ttu-id="ec7dc-119">Se houver mais que uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] em execução no servidor, será necessário identificar o processo pelo ID da instância que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-119">If there is more than one instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] running on the server, you need to identify the process by the ID of the instance you want to use.</span></span>  
  
    4.  <span data-ttu-id="ec7dc-120">Na caixa de texto **anexar a** , verifique se o tipo de programa apropriado está selecionado.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-120">In the **Attach to** text box, make sure that the appropriate program type is selected.</span></span> <span data-ttu-id="ec7dc-121">Para uma DLL CLR, clique em **selecionar**, clique em **depurar esses tipos de código**, clique em **gerenciado**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-121">For a CLR DLL, click **Select**, then click **Debug these code types**, then click **Managed**, then click **OK**.</span></span> <span data-ttu-id="ec7dc-122">Para uma DLL COM, clique em **selecionar**, clique em **depurar esses tipos de código**, clique em **nativo**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-122">For a COM DLL, click **Select**, then click **Debug these code types**, then click **Native**, then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="ec7dc-123">Clique em **Anexar**.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-123">Click **Attach**.</span></span>  
  
7.  <span data-ttu-id="ec7dc-124">No [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], acione o programa ou script MDX que chama o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-124">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], invoke the program or MDX script that calls the stored procedure.</span></span> <span data-ttu-id="ec7dc-125">O depurador será interrompido quando chegar a uma linha que contém um ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-125">The debugger breaks when it reaches a line containing a breakpoint.</span></span> <span data-ttu-id="ec7dc-126">Você pode avaliar variáveis na janela de informação, exibir os locais e navegar pelo código.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-126">You can evaluate variables in the watch window, view locals, and step through the code.</span></span>  
  
 <span data-ttu-id="ec7dc-127">Se houver problemas ao depurar uma biblioteca, certifique-se de que o arquivo do banco de dados do programa correspondente (arquivo PDB) foi copiado para o local de implantação no servidor.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-127">If you have problems debugging a library, make sure that the corresponding program database (PDB) file was copied to the deployment location on the server.</span></span> <span data-ttu-id="ec7dc-128">Se esse arquivo não foi copiado durante o registro ou a implantação, copie-o manualmente no mesmo local onde está a DLL.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-128">If this file was not copied during registration or deployment, you must copy it manually to the same location as the DLL.</span></span> <span data-ttu-id="ec7dc-129">No caso de código nativo (DLL COM), o arquivo PDB reside no subdiretório \debug.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-129">For native code (COM DLL), the PDB file resides in the \debug subdirectory.</span></span> <span data-ttu-id="ec7dc-130">Para código gerenciado (DLL CLR), reside no subdiretório \WINDEBUG.</span><span class="sxs-lookup"><span data-stu-id="ec7dc-130">For managed code (CLR DLL), it resides in the \WINDEBUG subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7dc-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ec7dc-131">See Also</span></span>  
 <span data-ttu-id="ec7dc-132">[Gerenciamento de assemblies de modelo multidimensional](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="ec7dc-132">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="ec7dc-133">Definindo procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="ec7dc-133">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
