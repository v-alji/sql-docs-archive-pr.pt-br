---
title: Referenciar outros assemblies em soluções de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, .NET Framework
- Script task [Integration Services], adding references
- referencing custom assemblies
- SSIS Script task, VisualBasic namespace
- assemblies [Integration Services]
- VisualBasic namespace
- Script task [Integration Services], VisualBasic namespace
- Microsoft.VisualBasic namespace
- Script task [Integration Services], .NET Framework
- .NET Framework [Integration Services]
- referencing Web services
ms.assetid: 9b655bcd-19f6-43d8-9f89-1b4d299c6380
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 685bbaa62da88e84cd848eb49dcf5bedb03d5390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570764"
---
# <a name="referencing-other-assemblies-in-scripting-solutions"></a><span data-ttu-id="e6ffa-102">Referenciando outros assemblies em soluções de script</span><span class="sxs-lookup"><span data-stu-id="e6ffa-102">Referencing Other Assemblies in Scripting Solutions</span></span>
  <span data-ttu-id="e6ffa-103">A biblioteca de classes [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fornece ao desenvolvedor de scripts um conjunto avançado de ferramentas para implementar uma funcionalidade personalizada em pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6ffa-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library provides the script developer with a powerful set of tools for implementing custom functionality in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="e6ffa-104">A tarefa Script e o componente Script também podem usar assemblies gerenciados personalizados.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-104">The Script task and the Script component can also use custom managed assemblies.</span></span>

> [!NOTE]
>  <span data-ttu-id="e6ffa-105">Para permitir que seus pacotes utilizem os objetos e métodos de um serviço Web, utilize o comando **Adicionar Referência Web** disponível em VSTA ([!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications).</span><span class="sxs-lookup"><span data-stu-id="e6ffa-105">To enable your packages to use the objects and methods from a Web service, use the **Add Web Reference** command available in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="e6ffa-106">Em versões anteriores do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], você teve que gerar uma classe proxy para usar um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-106">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you had to generate a proxy class to use a Web service.</span></span>

## <a name="using-a-managed-assembly"></a><span data-ttu-id="e6ffa-107">Usando um assembly gerenciado</span><span class="sxs-lookup"><span data-stu-id="e6ffa-107">Using a Managed Assembly</span></span>
 <span data-ttu-id="e6ffa-108">Para que o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] localize um assembly gerenciado em tempo de design, você deve seguir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e6ffa-108">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find a managed assembly at design time, you must do the following steps:</span></span>

1.  <span data-ttu-id="e6ffa-109">Armazene o assembly gerenciado em qualquer pasta de seu computador.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-109">Store the managed assembly in any folder on your computer.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="e6ffa-110">Em versões anteriores do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], só era possível adicionar uma referência a um assembly gerenciado que estivesse armazenado na pasta %windir%\Microsoft.NET\Framework\vx.x.xxxxx ou na pasta %ProgramFiles%\Microsoft SQL Server\100\SDK\Assemblies.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-110">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you could only add a reference to a managed assembly that was stored in the %windir%\Microsoft.NET\Framework\vx.x.xxxxx folder or the %ProgramFiles%\Microsoft SQL Server\100\SDK\Assemblies folder.</span></span>

2.  <span data-ttu-id="e6ffa-111">Adicione uma referência ao assembly gerenciado.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-111">Add a reference to the managed assembly.</span></span>

     <span data-ttu-id="e6ffa-112">Para adicionar a referência, no VSTA, na caixa de diálogo **Adicionar Referência**, na guia **Procurar**, localize e adicione o assembly gerenciado.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-112">To add the reference, in VSTA, in the **Add Reference** dialog box, on the **Browse** tab, locate and add the managed assembly.</span></span>

 <span data-ttu-id="e6ffa-113">Para que o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] encontre o assembly gerenciado em tempo de execução, você deve seguir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e6ffa-113">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find the managed assembly at run time, you must do the following steps:</span></span>

1.  <span data-ttu-id="e6ffa-114">Assine o assembly gerenciado com um nome forte.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-114">Sign the managed assembly with a strong name.</span></span>

2.  <span data-ttu-id="e6ffa-115">Instale o assembly no cache de assembly global do computador no qual o pacote é executado.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-115">Install the assembly in the global assembly cache on the computer on which the package is run.</span></span>

     <span data-ttu-id="e6ffa-116">Para obter mais informações, consulte [Compilar, implantar e depurar objetos personalizados](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="e6ffa-116">For more information, see [Building, Deploying, and Debugging Custom Objects](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span></span>

## <a name="using-the-microsoft-net-framework-class-library"></a><span data-ttu-id="e6ffa-117">Usando a biblioteca de classes do Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e6ffa-117">Using the Microsoft .NET Framework Class Library</span></span>
 <span data-ttu-id="e6ffa-118">A tarefa Script e o componente Script podem levar vantagem sobre todos os outros objetos e funcionalidades expostos pela biblioteca de classes [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6ffa-118">The Script task and the Script component can take advantage of all the other objects and functionality exposed by the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="e6ffa-119">Por exemplo, usando o [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], você pode recuperar informações sobre seu ambiente e pode interagir com o computador que está executando o pacote.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-119">For example, by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can retrieve information about your environment and interact with the computer that is running the package.</span></span>

 <span data-ttu-id="e6ffa-120">Esta lista descreve várias das classes [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] usadas com mais frequência:</span><span class="sxs-lookup"><span data-stu-id="e6ffa-120">This list describes several of the more frequently used [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes:</span></span>

-   <span data-ttu-id="e6ffa-121">`System.Data`Contém a arquitetura ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-121">`System.Data` Contains the ADO.NET architecture.</span></span>

-   <span data-ttu-id="e6ffa-122">`System.IO`Fornece uma interface para o sistema de arquivos e fluxos.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-122">`System.IO` Provides an interface to the file system and streams.</span></span>

-   <span data-ttu-id="e6ffa-123">`System.Windows.Forms`Fornece criação de formulário.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-123">`System.Windows.Forms` Provides form creation.</span></span>

-   <span data-ttu-id="e6ffa-124">`System.Text.RegularExpressions`Fornece classes para trabalhar com expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-124">`System.Text.RegularExpressions` Provides classes for working with regular expressions.</span></span>

-   <span data-ttu-id="e6ffa-125">`System.Environment`Retorna informações sobre o computador local, o usuário atual e as configurações do computador e do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-125">`System.Environment` Returns information about the local computer, the current user, and computer and user settings.</span></span>

-   <span data-ttu-id="e6ffa-126">`System.Net`Fornece comunicações de rede.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-126">`System.Net` Provides network communications.</span></span>

-   <span data-ttu-id="e6ffa-127">`System.DirectoryServices`Expõe Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-127">`System.DirectoryServices` Exposes Active Directory.</span></span>

-   <span data-ttu-id="e6ffa-128">`System.Drawing`Fornece bibliotecas de manipulação de imagem extensivas.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-128">`System.Drawing` Provides extensive image manipulation libraries.</span></span>

-   <span data-ttu-id="e6ffa-129">`System.Threading`Habilita a programação multi-threaded.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-129">`System.Threading` Enables multithreaded programming.</span></span>

 <span data-ttu-id="e6ffa-130">Para obter mais informações sobre o [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], consulte a Biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-130">For more information about the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see the MSDN Library.</span></span>

<span data-ttu-id="e6ffa-131">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e6ffa-131">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e6ffa-132">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="e6ffa-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e6ffa-133">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="e6ffa-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e6ffa-134">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="e6ffa-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6ffa-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e6ffa-135">See Also</span></span>
 [<span data-ttu-id="e6ffa-136">Estendendo pacotes com scripts</span><span class="sxs-lookup"><span data-stu-id="e6ffa-136">Extending Packages with Scripting</span></span>](extending-packages-with-scripting.md)


