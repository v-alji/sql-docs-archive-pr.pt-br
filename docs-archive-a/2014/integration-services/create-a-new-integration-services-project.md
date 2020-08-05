---
title: Criar um novo projeto de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Integration Services], creating
- Integration Services projects, creating
- SQL Server Integration Services projects, creating
- SSIS projects, creating
ms.assetid: 1e23f259-0401-4333-ab4f-89809aae63b1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f62d3ac2d33bb51a0ccc3b77d9f8b5ec0f52b345
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572624"
---
# <a name="create-a-new-integration-services-project"></a><span data-ttu-id="a0b59-102">Criar um novo projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="a0b59-102">Create a New Integration Services Project</span></span>
  <span data-ttu-id="a0b59-103">Este procedimento cria um novo projeto e uma nova solução do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0b59-103">This procedure creates a new project and a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] solution.</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="a0b59-104">Para criar um novo projeto Integration Services</span><span class="sxs-lookup"><span data-stu-id="a0b59-104">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="a0b59-105">Abra o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0b59-105">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="a0b59-106">No menu **Arquivo** , aponte para **Novo**e clique em **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a0b59-106">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="a0b59-107">Na caixa de diálogo **Novo Projeto**, no painel **Modelos**, selecione o modelo **Projeto do Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="a0b59-107">In the **New Project** dialog box, in the **Templates** pane, select the **Integration Services Project** template.</span></span>  
  
     <span data-ttu-id="a0b59-108">O modelo **Projeto do Integration Services** cria um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém um único pacote vazio.</span><span class="sxs-lookup"><span data-stu-id="a0b59-108">The **Integration Services Project** template creates an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains a single, empty package.</span></span>  
  
4.  <span data-ttu-id="a0b59-109">(Opcional) Edite o nome do projeto e o local.</span><span class="sxs-lookup"><span data-stu-id="a0b59-109">(Optional) Edit the project name and the location.</span></span>  
  
     <span data-ttu-id="a0b59-110">O nome da solução é automaticamente atualizado para corresponder ao nome do projeto.</span><span class="sxs-lookup"><span data-stu-id="a0b59-110">The solution name is automatically updated to match the project name.</span></span>  
  
5.  <span data-ttu-id="a0b59-111">Para criar uma pasta separada para o arquivo de solução, selecione **Criar diretório para solução**.</span><span class="sxs-lookup"><span data-stu-id="a0b59-111">To create a separate folder for the solution file, select **Create directory for solution**.</span></span> <span data-ttu-id="a0b59-112">Essa é a opção padrão.</span><span class="sxs-lookup"><span data-stu-id="a0b59-112">This is the default option.</span></span>  
  
6.  <span data-ttu-id="a0b59-113">Se o software de controle do código-fonte estiver instalado no computador, selecione **Adicionar ao controle do código-fonte** para associar o projeto ao controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="a0b59-113">If source control software is installed on the computer, select **Add to source control**  to associate the project with source control.</span></span>  
  
7.  <span data-ttu-id="a0b59-114">Se o software de controle do código-fonte for o [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, a caixa de diálogo **Logon do Visual SourceSafe** será aberta.</span><span class="sxs-lookup"><span data-stu-id="a0b59-114">If the source control software is [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, the **Visual SourceSafe Login** dialog box opens.</span></span> <span data-ttu-id="a0b59-115">Em **Logon do Visual SourceSafe**, forneça um nome de usuário, uma senha e o nome do banco de dados do [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="a0b59-115">In **Visual SourceSafe Login**, provide a user name, a password, and the name of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database.</span></span> <span data-ttu-id="a0b59-116">Clique em **Procurar** para localizar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a0b59-116">Click **Browse** to locate the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0b59-117">Para exibir e alterar o plug-in de controle do código-fonte selecionado e configurar o ambiente de controle do código-fonte, clique em **Opções** no menu **Ferramentas** e expanda o nó **Controle do Código-fonte**.</span><span class="sxs-lookup"><span data-stu-id="a0b59-117">To view and change the selected source control plug-in and to configure the source control environment, click **Options** on the **Tools** menu, and then expand the **Source Control** node.</span></span>  
  
8.  <span data-ttu-id="a0b59-118">Clique em **OK** para adicionar a solução para **explorar**o r e adicionar o projeto à solução.</span><span class="sxs-lookup"><span data-stu-id="a0b59-118">Click **OK** to add the solution to **Solution Explore**r and add the project to the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b59-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0b59-119">See Also</span></span>  
 <span data-ttu-id="a0b59-120">[Projetos do Integration Services &#40;SSIS&#41;](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="a0b59-120">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="a0b59-121">Adicionar ou remover um projeto do Integration Services em uma solução</span><span class="sxs-lookup"><span data-stu-id="a0b59-121">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
