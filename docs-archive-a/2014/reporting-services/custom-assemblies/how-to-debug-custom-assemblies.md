---
title: 'Como fazer: Depurar Assemblies Personalizados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services], debugging
- debugging custom assemblies [Reporting Services]
- troubleshooting [Reporting Services], custom assemblies
ms.assetid: 3a3215b3-548c-4474-81ba-3a98dd3912bf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b5f9f5a4595d59cce98da4f753422cd07529926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681448"
---
# <a name="how-to-debug-custom-assemblies"></a><span data-ttu-id="67b24-102">Como fazer: Depurar assemblies personalizados</span><span class="sxs-lookup"><span data-stu-id="67b24-102">How to: Debug Custom Assemblies</span></span>
  <span data-ttu-id="67b24-103">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fornece várias ferramentas de depuração que podem ajudá-lo a analisar seu código de assembly personalizado e localizar erros nele.</span><span class="sxs-lookup"><span data-stu-id="67b24-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your custom assembly code and locate errors in it.</span></span> <span data-ttu-id="67b24-104">A melhor ferramenta a ser usada dependerá do que você estiver tentando realizar.</span><span class="sxs-lookup"><span data-stu-id="67b24-104">The best tool to use will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="67b24-105">Este exemplo usa o [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b24-105">This example uses [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span>  
  
 <span data-ttu-id="67b24-106">A maneira recomendada de projetar, desenvolver e testar assemblies personalizados para o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é criar uma solução que contenha os seus relatórios de teste e o seu assembly personalizado.</span><span class="sxs-lookup"><span data-stu-id="67b24-106">The recommended way to design, develop, and test custom assemblies for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is to create a solution that contains both your test reports and your custom assembly.</span></span>  
  
### <a name="to-debug-assemblies-using-a-single-instance-of-visual-studio"></a><span data-ttu-id="67b24-107">Para depurar assemblies usando uma única instância de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="67b24-107">To debug assemblies using a single instance of Visual Studio</span></span>  
  
1.  <span data-ttu-id="67b24-108">Crie um novo projeto de relatório usando o [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b24-108">Create a new report project using [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
     <span data-ttu-id="67b24-109">No momento em que você cria um projeto de relatório, o [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] também cria uma solução para contê-lo.</span><span class="sxs-lookup"><span data-stu-id="67b24-109">At the time you create a report project, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] also creates a solution to contain it.</span></span>  
  
2.  <span data-ttu-id="67b24-110">Adicione um novo projeto de Biblioteca de Classe à solução existente.</span><span class="sxs-lookup"><span data-stu-id="67b24-110">Add a new Class Library project to the existing solution.</span></span> <span data-ttu-id="67b24-111">Verifique se o projeto de relatório foi definido como o projeto de inicialização.</span><span class="sxs-lookup"><span data-stu-id="67b24-111">Make sure that the report project is set as the startup project.</span></span> <span data-ttu-id="67b24-112">Para obter mais informações sobre como realizar isso, consulte a documentação do seu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b24-112">For more information about how to accomplish this, see your [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation.</span></span>  
  
3.  <span data-ttu-id="67b24-113">No Gerenciador de Soluções, selecione a solução.</span><span class="sxs-lookup"><span data-stu-id="67b24-113">In Solution Explorer, select the solution.</span></span>  
  
4.  <span data-ttu-id="67b24-114">No menu **Exibir**, clique em **Página de Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="67b24-114">On the **View** menu, click **Property Pages**.</span></span>  
  
     <span data-ttu-id="67b24-115">A caixa de diálogo **Páginas de Propriedades da Solução** será aberta.</span><span class="sxs-lookup"><span data-stu-id="67b24-115">The **Solution Property Pages** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="67b24-116">No painel esquerdo, expanda **Propriedades Comuns**, se necessário e clique em **Dependências do Projeto**.</span><span class="sxs-lookup"><span data-stu-id="67b24-116">In the left pane, expand **Common Properties** if necessary, and click **Project Dependencies**.</span></span> <span data-ttu-id="67b24-117">Selecione o projeto de relatório na lista suspensa **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="67b24-117">Select the report project from the **Project** drop-down list.</span></span> <span data-ttu-id="67b24-118">Selecione o projeto de assembly na lista **Depende De**.</span><span class="sxs-lookup"><span data-stu-id="67b24-118">Select your assembly project in the **Depends On** list.</span></span>  
  
6.  <span data-ttu-id="67b24-119">Clique em **OK** para salvar as alterações e feche a caixa de diálogo **Páginas de Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="67b24-119">Click **OK** to save the changes, and close the **Property Pages** dialog.</span></span>  
  
7.  <span data-ttu-id="67b24-120">No Gerenciador de Soluções, selecione o seu projeto de assembly personalizado.</span><span class="sxs-lookup"><span data-stu-id="67b24-120">In Solution Explorer, select your custom assembly project.</span></span>  
  
8.  <span data-ttu-id="67b24-121">No menu **Exibir**, clique em **Página de Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="67b24-121">On the **View** menu, click **Property Pages**.</span></span>  
  
     <span data-ttu-id="67b24-122">A caixa de diálogo **Páginas de Propriedades do Projeto** será exibida.</span><span class="sxs-lookup"><span data-stu-id="67b24-122">The **Project Property Pages** dialog box opens.</span></span>  
  
9. <span data-ttu-id="67b24-123">Clique na guia **Criar** se você estiver em um projeto C# ou na guia **Compilar** se estiver em um projeto do [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b24-123">Click the **Build** tab if you're in a C# project or the **Compile** tab if you're in a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] project.</span></span>  
  
10. <span data-ttu-id="67b24-124">Na página **Build** / **Compilar** compilação, insira o caminho para a pasta Report Designer.</span><span class="sxs-lookup"><span data-stu-id="67b24-124">On the **Build**/**Compile** page, enter the path to the Report Designer folder.</span></span> <span data-ttu-id="67b24-125">Por padrão, o caminho é C:\Program Files\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE, que você deverá inserir na caixa de texto **Caminho de Saída**.</span><span class="sxs-lookup"><span data-stu-id="67b24-125">By default, this is C:\Program Files\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE) in the **Output Path** text box.</span></span> <span data-ttu-id="67b24-126">Isso compilará e implantará uma versão atualizada do seu assembly personalizado diretamente no Designer de Relatórios antes da execução do seu relatório.</span><span class="sxs-lookup"><span data-stu-id="67b24-126">This builds and deploys an updated version of your custom assembly directly to Report Designer before your report is executed.</span></span>  
  
11. <span data-ttu-id="67b24-127">Depois que você criar o seu relatório e desenvolver o seu assembly personalizado, defina os pontos de interrupção em seu código de assembly personalizado.</span><span class="sxs-lookup"><span data-stu-id="67b24-127">Once you have designed your report and developed your custom assembly, set breakpoints in your custom assembly code.</span></span>  
  
12. <span data-ttu-id="67b24-128">Execute o relatório no modo **DebugLocal** pressionando a tecla F5.</span><span class="sxs-lookup"><span data-stu-id="67b24-128">Run the report under **DebugLocal** mode by pressing the F5 key.</span></span> <span data-ttu-id="67b24-129">Quando o relatório for executado na janela pop-up de visualização, o depurador atingirá um dos pontos de interrupção que corresponda ao código executável em seu assembly.</span><span class="sxs-lookup"><span data-stu-id="67b24-129">When the report executes in the pop-up preview window, the debugger hits any breakpoints that correspond to executable code in your assembly.</span></span> <span data-ttu-id="67b24-130">Use F11 para percorrer o seu código de assembly personalizado.</span><span class="sxs-lookup"><span data-stu-id="67b24-130">Use F11 to step through your custom assembly code.</span></span>  
  
### <a name="to-debug-assemblies-using-two-instances-of-visual-studio"></a><span data-ttu-id="67b24-131">Para depurar assemblies usando duas instâncias do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="67b24-131">To debug assemblies using two instances of Visual Studio</span></span>  
  
1.  <span data-ttu-id="67b24-132">Inicie o [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] e abra o seu projeto de assembly personalizado.</span><span class="sxs-lookup"><span data-stu-id="67b24-132">Start [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] and open your custom assembly project.</span></span>  
  
2.  <span data-ttu-id="67b24-133">Crie o projeto e implante o seu assembly personalizado e o arquivo .pdb auxiliar no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="67b24-133">Build the project, and deploy your custom assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="67b24-134">Para obter mais informações sobre a implantação, consulte [Implantando um assembly personalizado](deploying-a-custom-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="67b24-134">For more information about deployment, see [Deploying a Custom Assembly](deploying-a-custom-assembly.md).</span></span>  
  
3.  <span data-ttu-id="67b24-135">Abra um projeto de relatório que use o seu assembly personalizado deixando o seu código de assembly personalizado aberto em uma instância separada do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b24-135">Open up a report project that uses your custom assembly while leaving your custom assembly code open in a separate instance of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="67b24-136">Navegue até a instância do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] que contém o seu projeto de assembly personalizado e defina alguns pontos de quebra em seu código.</span><span class="sxs-lookup"><span data-stu-id="67b24-136">Navigate to the instance of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] that contains your custom assembly project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="67b24-137">Com o projeto de assembly personalizado ainda na janela ativa, clique em **Anexar ao Processo** no menu **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="67b24-137">With the custom assembly project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="67b24-138">A caixa de diálogo **Anexar ao Processo** será aberta.</span><span class="sxs-lookup"><span data-stu-id="67b24-138">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="67b24-139">Na lista de processos, selecione o processo devenv.exe que corresponde ao Projeto de Relatório e clique em **Anexar**.</span><span class="sxs-lookup"><span data-stu-id="67b24-139">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="67b24-140">Defina as expressões que serão usadas no relatório a partir do assembly personalizado e crie o relatório.</span><span class="sxs-lookup"><span data-stu-id="67b24-140">Define the expressions that you will use in your report from your custom assembly and design your report.</span></span>  
  
8.  <span data-ttu-id="67b24-141">Quando terminar de criar o relatório, clique na guia **Visualizar**.</span><span class="sxs-lookup"><span data-stu-id="67b24-141">When you are finished designing your report, click the **Preview** tab.</span></span>  
  
     <span data-ttu-id="67b24-142">O relatório será executado e o código de assembly personalizado deve ser interrompido em seus pontos de quebra predefinidos.</span><span class="sxs-lookup"><span data-stu-id="67b24-142">The report executes, and the custom assembly code should break at your predefined break points.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="67b24-143">O uso da guia **Visualizar** não impõe permissões de código para o assembly.</span><span class="sxs-lookup"><span data-stu-id="67b24-143">Using the **Preview** tab does not enforce code permissions for the assembly.</span></span> <span data-ttu-id="67b24-144">Para obter um teste completo, que inclui os erros de segurança de acesso do código, inicie o projeto de relatório na definição de configuração **DebugLocal**.</span><span class="sxs-lookup"><span data-stu-id="67b24-144">For a complete test, which includes any code access security errors, start the report project under the **DebugLocal** configuration setting.</span></span>  
  
9. <span data-ttu-id="67b24-145">Percorra seu código usando a tecla F11.</span><span class="sxs-lookup"><span data-stu-id="67b24-145">Step through your code using the F11 key.</span></span> <span data-ttu-id="67b24-146">Para obter mais informações sobre como depurar usando o [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], consulte a documentação do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b24-146">For more information about debugging using [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b24-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67b24-147">See Also</span></span>  
 [<span data-ttu-id="67b24-148">Usando assemblies personalizados com relatórios</span><span class="sxs-lookup"><span data-stu-id="67b24-148">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
