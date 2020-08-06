---
title: 'Etapa 3: modificar o valor de configuração da propriedade de diretório | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ba2a091f-361c-4331-afe2-53b465164c36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a71a7a181322d60caca98da4ddf3261cbce99c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571437"
---
# <a name="step-3-modifying-the-directory-property-configuration-value"></a><span data-ttu-id="0aedd-102">Etapa 3: Modificar o valor de configuração da propriedade de diretório</span><span class="sxs-lookup"><span data-stu-id="0aedd-102">Step 3: Modifying the Directory Property Configuration Value</span></span>
  <span data-ttu-id="0aedd-103">Nesta tarefa, você modificará a definição de configuração, armazenada no arquivo SSISTutorial.dtsConfig, da propriedade Value da variável no nível de pacote `User::varFolderName`.</span><span class="sxs-lookup"><span data-stu-id="0aedd-103">In this task, you will modify the configuration setting, stored in the SSISTutorial.dtsConfig file, for the Value property of the package-level variable `User::varFolderName`.</span></span> <span data-ttu-id="0aedd-104">A variável atualiza a propriedade Directory do contêiner Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="0aedd-104">The variable updates the Directory property of the Foreach Loop container.</span></span> <span data-ttu-id="0aedd-105">O valor modificado apontará para a `New Sample Data` pasta que você criou na tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="0aedd-105">The modified value will point to the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="0aedd-106">Depois de modificar a definição de configuração e executar o pacote, a propriedade Directory será atualizada pela variável, usando o valor populado do arquivo de configuração, em vez do valor de diretório originalmente configurado no pacote.</span><span class="sxs-lookup"><span data-stu-id="0aedd-106">After you modify the configuration setting and run the package, the Directory property will be updated by the variable, using the value populated from the configuration file instead of the directory value originally configured in the package.</span></span>  
  
### <a name="to-modify-the-configuration-setting-of-the-directory-property"></a><span data-ttu-id="0aedd-107">Para modificar a definição de configuração da propriedade de diretório</span><span class="sxs-lookup"><span data-stu-id="0aedd-107">To modify the configuration setting of the Directory property</span></span>  
  
1.  <span data-ttu-id="0aedd-108">No Bloco de notas ou em qualquer outro editor de texto, localize e abra o arquivo de configuração SSISTutorial.dts criado usando o Assistente para Configuração de Pacote na tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="0aedd-108">In Notepad or any other text editor, locate and open the SSISTutorial.dtsConfig configuration file that you created by using the Package Configuration Wizard in the previous task.</span></span>  
  
2.  <span data-ttu-id="0aedd-109">Altere o valor do elemento **configurable** para corresponder ao caminho da `New Sample Data` pasta que você criou na tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="0aedd-109">Change the value of the **ConfiguredValue** element to match the path of the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="0aedd-110">Não coloque o caminho entre aspas.</span><span class="sxs-lookup"><span data-stu-id="0aedd-110">Do not surround the path in quotes.</span></span> <span data-ttu-id="0aedd-111">Se a `New Sample Data` pasta estiver no nível raiz da unidade (por exemplo, C: \\ ), o XML atualizado deverá ser semelhante ao seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="0aedd-111">If the `New Sample Data` folder is at the root level of your drive (for example, C:\\), the updated XML should be similar to the following sample:</span></span>  
  
     `<?xml version="1.0"?><DTSConfiguration><DTSConfigurationHeading><DTSConfigurationFileInfo GeneratedBy="DOMAIN\UserName" GeneratedFromPackageName="Lesson 5" GeneratedFromPackageID="{F4475E73-59E3-478F-8EB2-B10AFA61D3FA}" GeneratedDate="6/10/2012 8:16:50 AM"/></DTSConfigurationHeading><Configuration ConfiguredType="Property" Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"><ConfiguredValue></ConfiguredValue></Configuration></DTSConfiguration>`  
  
     <span data-ttu-id="0aedd-112">As informações de cabeçalho, `GeneratedBy` , `GeneratedFromPackageID` e **GeneratedDate** serão diferentes em seu arquivo, é claro.</span><span class="sxs-lookup"><span data-stu-id="0aedd-112">The heading information, `GeneratedBy`, `GeneratedFromPackageID`, and **GeneratedDate** will be different in your file, of course.</span></span> <span data-ttu-id="0aedd-113">O elemento a ser anotado é `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="0aedd-113">The element to note is the `Configuration` element.</span></span> <span data-ttu-id="0aedd-114">A propriedade `Value` da variável, `User::varFolderName`, agora contém C:\Novos Dados de Exemplo.</span><span class="sxs-lookup"><span data-stu-id="0aedd-114">The `Value` property of the variable, `User::varFolderName`, now contains C:\New Sample Data.</span></span>  
  
3.  <span data-ttu-id="0aedd-115">Salve a alteração e feche o editor de textos.</span><span class="sxs-lookup"><span data-stu-id="0aedd-115">Save the change, and then close the text editor.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0aedd-116">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="0aedd-116">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0aedd-117">Etapa 4: Testar o pacote de tutorial da Lição 5</span><span class="sxs-lookup"><span data-stu-id="0aedd-117">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](../integration-services/lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
  
