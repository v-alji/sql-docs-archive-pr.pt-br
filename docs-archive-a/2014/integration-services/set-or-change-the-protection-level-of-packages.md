---
title: Definir ou alterar o nível de proteção dos pacotes | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- passwords [Integration Services]
- packages [Integration Services],security
- security [Integration Services],protection levels
- protection level for packages [Integration Services]
ms.assetid: 904a5580-82ba-4a26-b0c5-d1c989975f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da8e63028498097b4321e4ef1383fbc8aa5845b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685209"
---
# <a name="set-or-change-the-protection-level-of-packages"></a><span data-ttu-id="2df8b-102">Definir ou alterar o nível de proteção de pacotes</span><span class="sxs-lookup"><span data-stu-id="2df8b-102">Set or Change the Protection Level of Packages</span></span>
  <span data-ttu-id="2df8b-103">Para controlar o acesso ao conteúdo de pacotes e aos valores confidenciais que eles contêm, como senhas, defina o valor da propriedade `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="2df8b-103">To control access to the contents of packages and to the sensitive values that they contain, such as passwords, set the value of the `ProtectionLevel` property.</span></span> <span data-ttu-id="2df8b-104">Os pacotes contidos em um projeto precisam ter o mesmo nível de proteção que o projeto, para criar o projeto.</span><span class="sxs-lookup"><span data-stu-id="2df8b-104">The packages contained in a project need to have the same protection level as the project, to build the project.</span></span> <span data-ttu-id="2df8b-105">Se você alterou os parâmetros da propriedade `ProtectionLevel` no projeto, precisa atualizar manualmente os parâmetros de propriedade para os pacotes.</span><span class="sxs-lookup"><span data-stu-id="2df8b-105">If you change the `ProtectionLevel` property setting on the project, you need to manually update the property setting for the packages.</span></span>  
  
 <span data-ttu-id="2df8b-106">Para obter informações sobre como determinar as `ProtectionLevel` configurações apropriadas para seus pacotes em diferentes estágios no ciclo de vida do pacote, consulte [controle de acesso para dados confidenciais em pacotes](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="2df8b-106">For information about how to determine the `ProtectionLevel` settings that are appropriate for your packages at different stages in the package life cycle, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span> <span data-ttu-id="2df8b-107">Para obter uma visão geral dos recursos de segurança no [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], consulte [Visão geral de segurança &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="2df8b-107">For an overview of security features in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], see [Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span></span>  
  
 <span data-ttu-id="2df8b-108">Os procedimentos deste tópico descrevem como usar o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ou o utilitário de prompt de comando dtutil para alterar a propriedade `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="2df8b-108">The procedures in this topic describe how to use either [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or the dtutil command prompt utility to change the `ProtectionLevel` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2df8b-109">Além dos procedimentos deste tópico, tipicamente você pode definir ou alterar a propriedade `ProtectionLevel` de um pacote ao importar ou exportar o pacote.</span><span class="sxs-lookup"><span data-stu-id="2df8b-109">In addition to the procedures in this topic, you can typically set or change the `ProtectionLevel` property of a package when you import or export the package.</span></span> <span data-ttu-id="2df8b-110">Você também pode alterar a propriedade de `ProtectionLevel` de um pacote ao usar o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para salvar um pacote.</span><span class="sxs-lookup"><span data-stu-id="2df8b-110">You can also change the `ProtectionLevel` property of a package when you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to save a package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-a-package-in-sql-server-data-tools"></a><span data-ttu-id="2df8b-111">Para definir ou alterar o nível de proteção de um pacote nas Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="2df8b-111">To set or change the protection level of a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="2df8b-112">Examine os valores disponíveis para a `ProtectionLevel` propriedade no tópico [definindo o nível de proteção dos pacotes](security/access-control-for-sensitive-data-in-packages.md)e determine o valor apropriado para o pacote.</span><span class="sxs-lookup"><span data-stu-id="2df8b-112">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="2df8b-113">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote.</span><span class="sxs-lookup"><span data-stu-id="2df8b-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package.</span></span>  
  
3.  <span data-ttu-id="2df8b-114">Abra o pacote no designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2df8b-114">Open the package in the [!INCLUDE[ssIS](../includes/ssis-md.md)] designer.</span></span>  
  
4.  <span data-ttu-id="2df8b-115">Se a janela Propriedades não mostrar as propriedades do pacote, clique na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="2df8b-115">If the Properties window does not show the properties of the package, click the design surface.</span></span>  
  
5.  <span data-ttu-id="2df8b-116">No janela Propriedades, no grupo **segurança** , selecione o valor apropriado para a `ProtectionLevel` propriedade.</span><span class="sxs-lookup"><span data-stu-id="2df8b-116">In the Properties window, in the **Security** group, select the appropriate value for the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="2df8b-117">Se você selecionar um nível de proteção que exija uma senha, insira a senha como o valor da propriedade **PackagePassword** .</span><span class="sxs-lookup"><span data-stu-id="2df8b-117">If you select a protection level that requires a password, enter the password as the value of the **PackagePassword** property.</span></span>  
  
6.  <span data-ttu-id="2df8b-118">No menu **Arquivo** , selecione **Salvar Itens Selecionados** para salvar o pacote modificado.</span><span class="sxs-lookup"><span data-stu-id="2df8b-118">On the **File** menu, select **Save Selected Items** to save the modified package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-packages-at-the-command-prompt"></a><span data-ttu-id="2df8b-119">Para definir ou alterar o nível de proteção de pacotes no prompt de comando</span><span class="sxs-lookup"><span data-stu-id="2df8b-119">To set or change the protection level of packages at the command prompt</span></span>  
  
1.  <span data-ttu-id="2df8b-120">Examine os valores disponíveis para a `ProtectionLevel` propriedade no tópico [definindo o nível de proteção dos pacotes](security/access-control-for-sensitive-data-in-packages.md)e determine o valor apropriado para o pacote.</span><span class="sxs-lookup"><span data-stu-id="2df8b-120">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="2df8b-121">Examine os mapeamentos da `Encrypt` opção no tópico [dtutil Utility](dtutil-utility.md)e determine o inteiro apropriado a ser usado como o valor da `ProtectionLevel` propriedade selecionada.</span><span class="sxs-lookup"><span data-stu-id="2df8b-121">Review the mappings for the `Encrypt` option in the topic, [dtutil Utility](dtutil-utility.md), and determine the appropriate integer to use as the value of the selected `ProtectionLevel` property.</span></span>  
  
3.  <span data-ttu-id="2df8b-122">Abra uma janela de Prompt de Comando.</span><span class="sxs-lookup"><span data-stu-id="2df8b-122">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="2df8b-123">No prompt de comando, navegue para a pasta que contém o pacote ou pacotes para os quais você deseja definir a propriedade `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="2df8b-123">At the command prompt, navigate to the folder that contains the package or packages for which you want to set the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="2df8b-124">Os exemplos de sintaxe mostrados na etapa a seguir assumem que essa é a pasta atual.</span><span class="sxs-lookup"><span data-stu-id="2df8b-124">The syntax examples shown in the following step assume that this folder is the current folder.</span></span>  
  
5.  <span data-ttu-id="2df8b-125">Defina ou altere o nível de proteção do pacote ou pacotes usando um comando semelhante ao dos seguintes exemplos:</span><span class="sxs-lookup"><span data-stu-id="2df8b-125">Set or change the protection level of the package or packages by using a command similar to the one of the following examples:</span></span>  
  
    -   <span data-ttu-id="2df8b-126">O comando a seguir define a propriedade `ProtectionLevel` de um pacote individual no sistema de arquivos como nível 2, "Criptografar dados confidenciais com senha", com a senha, "senha forte":</span><span class="sxs-lookup"><span data-stu-id="2df8b-126">The following command sets the `ProtectionLevel` property of an individual package in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `dtutil.exe /file "C:\Package.dtsx" /encrypt file;"C:\Package.dtsx";2;strongpassword`  
  
    -   <span data-ttu-id="2df8b-127">O comando a seguir define a propriedade `ProtectionLevel` de todos os pacotes em uma pasta específica no sistema de arquivos como nível 2, "Criptografar dados confidenciais com senha", com a senha, "senha forte":</span><span class="sxs-lookup"><span data-stu-id="2df8b-127">The following command sets the `ProtectionLevel` property of all packages in a particular folder in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `for %f in (*.dtsx) do dtutil.exe /file %f /encrypt file;%f;2;strongpassword`  
  
         <span data-ttu-id="2df8b-128">Se você usar um comando semelhante em um arquivo em lotes, digite o espaço reservado do arquivo, "%f", como "%%f" no arquivo em lotes.</span><span class="sxs-lookup"><span data-stu-id="2df8b-128">If you use a similar command in a batch file, enter the file placeholder, "%f", as "%%f" in the batch file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df8b-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2df8b-129">See Also</span></span>  
 [<span data-ttu-id="2df8b-130">Utilitário dtutil</span><span class="sxs-lookup"><span data-stu-id="2df8b-130">dtutil Utility</span></span>](dtutil-utility.md)  
  
  
