---
title: 'Lição 5: adicionando configurações de pacote para o modelo de implantação de pacote | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c10dd54-67cb-4b63-9e4d-aa6ff0452ecb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ee03d624ac7144cf6aef0829bcb7835fe5af9c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679428"
---
# <a name="lesson-5-adding-package-configurations-for-the-package-deployment-model"></a><span data-ttu-id="c148e-102">Lição 5: Como adicionar configurações de pacote para o modelo de implantação de pacote</span><span class="sxs-lookup"><span data-stu-id="c148e-102">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>
  <span data-ttu-id="c148e-103">As configurações de pacote deixam você definir propriedades de tempo de execução e variáveis de fora do ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="c148e-103">Package configurations let you set run-time properties and variables from outside of the development environment.</span></span> <span data-ttu-id="c148e-104">As configurações permitem que você desenvolva pacotes que flexíveis e fáceis de implantar e distribuir.</span><span class="sxs-lookup"><span data-stu-id="c148e-104">Configurations allow you to develop packages that are flexible and easy to both deploy and distribute.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="c148e-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] oferece os seguintes tipos de configuração:</span><span class="sxs-lookup"><span data-stu-id="c148e-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] offers the following configuration types:</span></span>  
  
-   <span data-ttu-id="c148e-106">Arquivo de configuração XML</span><span class="sxs-lookup"><span data-stu-id="c148e-106">XML configuration file</span></span>  
  
-   <span data-ttu-id="c148e-107">Variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="c148e-107">Environment variable</span></span>  
  
-   <span data-ttu-id="c148e-108">Entrada de Registro</span><span class="sxs-lookup"><span data-stu-id="c148e-108">Registry entry</span></span>  
  
-   <span data-ttu-id="c148e-109">Variável de pacote pai</span><span class="sxs-lookup"><span data-stu-id="c148e-109">Parent package variable</span></span>  
  
-   <span data-ttu-id="c148e-110">Tabela [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c148e-110">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table</span></span>  
  
 <span data-ttu-id="c148e-111">Nesta lição, você modificará o pacote simples do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] criados na [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) para usar o Modelo de Implantação de Pacote e aproveitar as configurações do pacote.</span><span class="sxs-lookup"><span data-stu-id="c148e-111">In this lesson, you will modify the simple [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you created in [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) to use the Package Deployment Model and take advantage of package configurations.</span></span> <span data-ttu-id="c148e-112">Você também pode copiar o pacote concluído da Lição 4 que está incluso no tutorial.</span><span class="sxs-lookup"><span data-stu-id="c148e-112">You can also copy the completed Lesson 4 package that is included with the tutorial.</span></span> <span data-ttu-id="c148e-113">Usando o Assistente de Configuração de Pacote, você irá criar uma configuração XML que atualiza a propriedade `Directory` do contêiner Loop Foreach utilizando uma variável de nível de pacote mapeada para a propriedade do Diretório.</span><span class="sxs-lookup"><span data-stu-id="c148e-113">Using the Package Configuration Wizard, you will create an XML configuration that updates the `Directory` property of the Foreach Loop container by using a package-level variable mapped to the Directory property.</span></span> <span data-ttu-id="c148e-114">Depois de criar um arquivo de configuração, você modificará o valor da variável de fora do ambiente de desenvolvimento e apontará a propriedade modificada para uma nova pasta de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="c148e-114">Once you have created the configuration file, you will modify the value of the variable from outside of the development environment and point the modified property to a new sample data folder.</span></span> <span data-ttu-id="c148e-115">Quando você executa o pacote novamente, o arquivo de configuração popula o valor da variável e a variável, por sua vez, atualiza a `Directory` propriedade.</span><span class="sxs-lookup"><span data-stu-id="c148e-115">When you run the package again, the configuration file populates the value of the variable, and the variable in turn updates the `Directory` property.</span></span> <span data-ttu-id="c148e-116">Como resultado, o pacote itera através dos arquivos na nova pasta de dados, em vez de iterar através de arquivos na pasta original que foi codificada no pacote.</span><span class="sxs-lookup"><span data-stu-id="c148e-116">As a result, the package iterates through the files in the new data folder, rather than iterating through the files in the original folder that was hard-coded in the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c148e-117">Este tutorial requer o banco de dados de exemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="c148e-117">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="c148e-118">Para obter mais informações sobre como instalar e implantar o **AdventureWorksDW2012**, consulte [Amostras de produto do Reporting Services no CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="c148e-118">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="c148e-119">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="c148e-119">Lesson Tasks</span></span>  
 <span data-ttu-id="c148e-120">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="c148e-120">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="c148e-121">Etapa 1: Copiar o pacote da Lição 4</span><span class="sxs-lookup"><span data-stu-id="c148e-121">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
-   [<span data-ttu-id="c148e-122">Etapa 2: Habilitar e configurar configurações de pacote</span><span class="sxs-lookup"><span data-stu-id="c148e-122">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
-   [<span data-ttu-id="c148e-123">Etapa 3: Modificar o valor de configuração da propriedade de diretório</span><span class="sxs-lookup"><span data-stu-id="c148e-123">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
-   [<span data-ttu-id="c148e-124">Etapa 4: Testar o pacote de tutorial da Lição 5</span><span class="sxs-lookup"><span data-stu-id="c148e-124">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="c148e-125">Iniciar a lição</span><span class="sxs-lookup"><span data-stu-id="c148e-125">Start the Lesson</span></span>  
  
-   [<span data-ttu-id="c148e-126">Etapa 1: Copiar o pacote da Lição 4</span><span class="sxs-lookup"><span data-stu-id="c148e-126">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
  
