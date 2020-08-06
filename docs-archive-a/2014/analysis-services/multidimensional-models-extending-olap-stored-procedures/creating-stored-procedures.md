---
title: Criando procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- registering assemblies
- database assemblies [Analysis Services]
- server assemblies [Analysis Services]
- stored procedures [Analysis Services], creating
- assemblies [Analysis Services]
ms.assetid: a12ff02f-6d0b-4488-9846-3609fc0d0554
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9a997244a2d54cca8732196107dd21927b5f9e2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680699"
---
# <a name="creating-stored-procedures"></a><span data-ttu-id="c8849-102">Criando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="c8849-102">Creating Stored Procedures</span></span>
  <span data-ttu-id="c8849-103">Todos os procedimentos armazenados devem ser associados a uma classe CLR (Common Language Runtime) ou COM (Component Object Model) para poderem seu usados.</span><span class="sxs-lookup"><span data-stu-id="c8849-103">All stored procedures must be associated with a common language runtime (CLR) or Component Object Model (COM) class in order to be used.</span></span> <span data-ttu-id="c8849-104">A classe deve ser instalada no servidor – geralmente na forma de um [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® biblioteca de vínculo dinâmico (DLL) e registrada como um assembly no servidor ou em um banco de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dados.</span><span class="sxs-lookup"><span data-stu-id="c8849-104">The class must be installed on the server - usually in the form of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® dynamic link library (DLL) - and registered as an assembly on the server or in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="c8849-105">Procedimentos armazenados são registrados em um servidor ou em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c8849-105">Stored procedures are registered on a server or on a database.</span></span> <span data-ttu-id="c8849-106">Procedimentos armazenados do servidor podem ser chamados a partir de qualquer contexto de consulta.</span><span class="sxs-lookup"><span data-stu-id="c8849-106">Server stored procedures can be called from any query context.</span></span> <span data-ttu-id="c8849-107">Procedimentos armazenados do banco de dados podem ser acessados somente se o contexto do banco de dados for o banco de dados no qual o procedimento armazenado foi definido.</span><span class="sxs-lookup"><span data-stu-id="c8849-107">Database stored procedures can only be accessed if the database context is the database under which the stored procedure is defined.</span></span> <span data-ttu-id="c8849-108">Se as funções de um assembly chamarem funções de um assembly diferente, registre ambos no mesmo contexto (servidor ou banco de dados).</span><span class="sxs-lookup"><span data-stu-id="c8849-108">If functions in one assembly call functions in a different assembly, you must register both assemblies in the same context (server or database).</span></span> <span data-ttu-id="c8849-109">Para um servidor ou um banco de dados implantado [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] em um servidor, você pode usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o para registrar um assembly.</span><span class="sxs-lookup"><span data-stu-id="c8849-109">For a server or a deployed [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database on a server, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to register an assembly.</span></span> <span data-ttu-id="c8849-110">Para um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], você pode usar o Designer do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para registrar um assembly no projeto.</span><span class="sxs-lookup"><span data-stu-id="c8849-110">For an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you can use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Designer to register an assembly in the project.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c8849-111">Os assemblies COM podem representar um risco à segurança.</span><span class="sxs-lookup"><span data-stu-id="c8849-111">COM assemblies might pose a security risk.</span></span> <span data-ttu-id="c8849-112">Devido a esse risco e outras considerações, os assemblies COM foram preteridos no [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8849-112">Due to this risk and other considerations, COM assemblies were deprecated in [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)].</span></span> <span data-ttu-id="c8849-113">Talvez não haja suporte para assemblies COM em versões futuras.</span><span class="sxs-lookup"><span data-stu-id="c8849-113">COM assemblies might not be supported in future releases.</span></span>  
  
## <a name="registering-a-server-assembly"></a><span data-ttu-id="c8849-114">Registrando um assembly de servidor</span><span class="sxs-lookup"><span data-stu-id="c8849-114">Registering a Server Assembly</span></span>  
 <span data-ttu-id="c8849-115">No Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], os assemblies de servidor são listados na pasta Assemblies sob uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8849-115">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], server assemblies are listed in the Assemblies folder under an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c8849-116">Os assemblies de servidor podem conter assemblies .NET (CLR) e bibliotecas COM.</span><span class="sxs-lookup"><span data-stu-id="c8849-116">Server assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-server-assembly"></a><span data-ttu-id="c8849-117">Para criar um assembly de servidor</span><span class="sxs-lookup"><span data-stu-id="c8849-117">To create a server assembly</span></span>  
  
1.  <span data-ttu-id="c8849-118">Expanda a instância do no Pesquisador de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objetos, clique com o botão direito do mouse na pasta **assemblies** e clique em **novo assembly**.</span><span class="sxs-lookup"><span data-stu-id="c8849-118">Expand the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="c8849-119">Isso exibe a caixa de diálogo **registrar assembly do servidor** .</span><span class="sxs-lookup"><span data-stu-id="c8849-119">This displays the **Register Server Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="c8849-120">Para o **tipo** , especifique o tipo de assembly:</span><span class="sxs-lookup"><span data-stu-id="c8849-120">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="c8849-121">Como DLL de código gerenciado (CLR), especifique .NET Assembly.</span><span class="sxs-lookup"><span data-stu-id="c8849-121">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="c8849-122">Para uma DLL de código nativo (COM), especifique a DLL COM.</span><span class="sxs-lookup"><span data-stu-id="c8849-122">For a native code (COM) DLL, specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="c8849-123">Para **nome do arquivo**, ESPECIFIQUE a DLL que contém os procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="c8849-123">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="c8849-124">Para **nome do assembly**, especifique um nome para o assembly.</span><span class="sxs-lookup"><span data-stu-id="c8849-124">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="c8849-125">Se essa for uma compilação de depuração da biblioteca que você pretende usar para depurar procedimentos armazenados, marque a caixa de seleção **incluir informações de depuração** .</span><span class="sxs-lookup"><span data-stu-id="c8849-125">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="c8849-126">Para obter mais informações sobre como depurar procedimentos armazenados, consulte [Depurando procedimentos armazenados](debugging-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c8849-126">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="c8849-127">Você pode clicar em **OK** para registrar o assembly imediatamente ou na barra de ferramentas da caixa de diálogo, você pode clicar em um comando no menu **script** para gerar o script da ação de registro para uma janela de consulta, um arquivo ou a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="c8849-127">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="c8849-128">Depois de registrar um assembly de servidor, você pode configurá-lo clicando com o botão direito do mouse no assembly no Pesquisador de objetos e clicando em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c8849-128">After you register a server assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-on-the-server"></a><span data-ttu-id="c8849-129">Registrando um assembly de banco de dados no servidor</span><span class="sxs-lookup"><span data-stu-id="c8849-129">Registering a Database Assembly on the Server</span></span>  
 <span data-ttu-id="c8849-130">No Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], os assemblies de banco de dados são listados na pasta Assemblies sob um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8849-130">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="c8849-131">Os assemblies de banco de dados podem conter assemblies .NET (CLR) e bibliotecas COM.</span><span class="sxs-lookup"><span data-stu-id="c8849-131">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-on-a-server"></a><span data-ttu-id="c8849-132">Para criar um assembly de banco de dados em um servidor</span><span class="sxs-lookup"><span data-stu-id="c8849-132">To create a database assembly on a server</span></span>  
  
1.  <span data-ttu-id="c8849-133">Expanda a instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados no Pesquisador de objetos, clique com o botão direito do mouse na pasta **assemblies** e clique em **novo assembly**.</span><span class="sxs-lookup"><span data-stu-id="c8849-133">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="c8849-134">Isso exibe a caixa de diálogo **registrar assembly de banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="c8849-134">This displays the **Register Database Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="c8849-135">Para o **tipo** , especifique o tipo de assembly:</span><span class="sxs-lookup"><span data-stu-id="c8849-135">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="c8849-136">Como DLL de código gerenciado (CLR), especifique .NET Assembly.</span><span class="sxs-lookup"><span data-stu-id="c8849-136">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="c8849-137">Como DLL de código nativo (COM), especifique COM DLL.</span><span class="sxs-lookup"><span data-stu-id="c8849-137">For a native code (COM) DLL), specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="c8849-138">Para **nome do arquivo**, ESPECIFIQUE a DLL que contém os procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="c8849-138">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="c8849-139">Para **nome do assembly**, especifique um nome para o assembly.</span><span class="sxs-lookup"><span data-stu-id="c8849-139">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="c8849-140">Se essa for uma compilação de depuração da biblioteca que você pretende usar para depurar procedimentos armazenados, marque a caixa de seleção **incluir informações de depuração** .</span><span class="sxs-lookup"><span data-stu-id="c8849-140">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="c8849-141">Para obter mais informações sobre como depurar procedimentos armazenados, consulte [Depurando procedimentos armazenados](debugging-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c8849-141">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="c8849-142">Você pode clicar em **OK** para registrar o assembly imediatamente ou na barra de ferramentas da caixa de diálogo, você pode clicar em um comando no menu **script** para gerar o script da ação de registro para uma janela de consulta, um arquivo ou a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="c8849-142">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="c8849-143">Depois de registrar um assembly de banco de dados, você pode configurá-lo clicando com o botão direito do mouse no assembly no Pesquisador de objetos e clicando em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c8849-143">After you register a database assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-in-a-project"></a><span data-ttu-id="c8849-144">Registrando um assembly de banco de dados em um projeto</span><span class="sxs-lookup"><span data-stu-id="c8849-144">Registering a Database Assembly in a Project</span></span>  
 <span data-ttu-id="c8849-145">No Gerenciador de Soluções do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], os assemblies de banco de dados são listados na pasta Assemblies sob um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8849-145">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="c8849-146">Os assemblies de banco de dados podem conter assemblies .NET (CLR) e bibliotecas COM.</span><span class="sxs-lookup"><span data-stu-id="c8849-146">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-in-an-analysis-service-project"></a><span data-ttu-id="c8849-147">Para criar um assembly de banco de dados em um projeto do Analysis Service</span><span class="sxs-lookup"><span data-stu-id="c8849-147">To create a database assembly in an Analysis Service project</span></span>  
  
1.  <span data-ttu-id="c8849-148">Expanda a instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados no Pesquisador de objetos, clique com o botão direito do mouse na pasta **assemblies** e clique em **nova referência de assembly**.</span><span class="sxs-lookup"><span data-stu-id="c8849-148">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly Reference**.</span></span> <span data-ttu-id="c8849-149">Isso exibe a caixa de diálogo **Adicionar referência** .</span><span class="sxs-lookup"><span data-stu-id="c8849-149">This displays the **Add Reference** dialog box.</span></span> <span data-ttu-id="c8849-150">A guia **.net** da caixa de diálogo **Adicionar referência** lista os assemblies .net (CLR) existentes, enquanto a guia **projetos** lista os projetos.</span><span class="sxs-lookup"><span data-stu-id="c8849-150">The **.NET** tab of the **Add Reference** dialog box lists existing .NET (CLR) assemblies, while the **Projects** tab lists projects.</span></span>  
  
2.  <span data-ttu-id="c8849-151">Você pode clicar em um componente ou projeto existente e, em seguida, clicar em **Adicionar** para adicioná-lo ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="c8849-151">You can click an existing component or project and then click **Add** to add it to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="c8849-152">Para adicionar uma referência a uma DLL COM, clique na guia **procurar** para localizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="c8849-152">To add a reference to a COM DLL, click the **Browse** tab to find the file.</span></span> <span data-ttu-id="c8849-153">A lista **projetos e componentes selecionados** mostra o nome, o tipo, a versão e o local de cada componente que você está adicionando ao projeto.</span><span class="sxs-lookup"><span data-stu-id="c8849-153">The **Selected projects and components** list shows the name, type, version, and location for each component that you are adding to the project.</span></span>  
  
3.  <span data-ttu-id="c8849-154">Quando terminar de selecionar os componentes a serem adicionados, clique em **OK** para adicioná-los ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="c8849-154">When you are finished selecting components to add, click **OK** to add them to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
## <a name="script-format-for-an-assembly"></a><span data-ttu-id="c8849-155">Formato de script para um assembly</span><span class="sxs-lookup"><span data-stu-id="c8849-155">Script Format For an Assembly</span></span>  
 <span data-ttu-id="c8849-156">Registrar um assembly .NET é bastante simples.</span><span class="sxs-lookup"><span data-stu-id="c8849-156">Registering a .NET assembly is fairly simple.</span></span> <span data-ttu-id="c8849-157">Um assembly .NET é adicionado a um banco de dados em formato binário que usa o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="c8849-157">A .NET assembly is added to a database in binary format using the following format:</span></span>  
  
```  
<Create>  
   <ObjectDefinition>  
      <Assembly>  
         <Files>  
            <File>  
               <Name>filename</Name>  
               <Type>filetype</Type>  
               <Data>  
                  <Block>binarydatablock</Block>  
                  <Block>binarydatablock</Block>  
                  ...  
               </Data>  
            </File>  
         </Files>  
         <PermissionSet>PermissionSet</PermissionSet>  
      </Assembly>  
   <ObjectDefinition>  
</Create>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8849-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8849-158">See Also</span></span>  
 <span data-ttu-id="c8849-159">[Gerenciamento de assemblies de modelo multidimensional](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="c8849-159">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="c8849-160">Definindo procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="c8849-160">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
