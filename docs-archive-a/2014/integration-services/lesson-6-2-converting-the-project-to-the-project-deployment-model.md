---
title: 'Etapa 2: converter o projeto para o modelo de implantação de projeto | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80964293-f1f5-4da7-b1fb-00ab8c30c1c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7b879b2bea4afd58a48cdfc6f0890353fe6758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570111"
---
# <a name="step-2-converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="b3559-102">Etapa 2: Convertendo o projeto para o modelo de implantação de projeto</span><span class="sxs-lookup"><span data-stu-id="b3559-102">Step 2: Converting the Project to the Project Deployment Model</span></span>
  <span data-ttu-id="b3559-103">Nesta tarefa, você usará o Assistente de conversão de projeto do Integration Services para converter o projeto para o modelo de implantação do projeto.</span><span class="sxs-lookup"><span data-stu-id="b3559-103">In this task, you will use the Integration Services Project Conversion Wizard to convert the project to the Project Deployment Model.</span></span>  
  
### <a name="converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="b3559-104">Convertendo o projeto para o modelo de implantação de projeto</span><span class="sxs-lookup"><span data-stu-id="b3559-104">Converting the Project to the Project Deployment Model</span></span>  
  
1.  <span data-ttu-id="b3559-105">No Menu Projeto, clique em Converter em modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="b3559-105">On the Project Menu, click Convert to Project Deployment Model.</span></span>  
  
2.  <span data-ttu-id="b3559-106">Na página de Introdução do Assistente de conversão de projeto do Integration Services, revise as etapas e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="b3559-106">On the Integration Services Project Conversion Wizard Introduction page, review the steps then click Next.</span></span>  
  
3.  <span data-ttu-id="b3559-107">Na página Selecionar pacotes, na lista Pacotes, desmarque todas as caixas de seleção exceto Lição 6.dtsx e então clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="b3559-107">On the Select Packages page, in the Packages list, clear all checkboxes except Lesson 6.dtsx then click Next.</span></span>  
  
4.  <span data-ttu-id="b3559-108">Na página Especificar propriedades do projeto, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="b3559-108">On the Specify Project Properties page, click Next.</span></span>  
  
5.  <span data-ttu-id="b3559-109">Na página Atualizar tarefa de execução do pacote, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="b3559-109">On the Update Execute Package Task page click Next.</span></span>  
  
6.  <span data-ttu-id="b3559-110">Na página Selecionar configurações, verifique se que o pacote da Lição 6.dtsx está selecionado na lista Configurações e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="b3559-110">On the Select Configurations page, make sure the Lesson 6.dtsx package is selected in the Configurations list, then click Next.</span></span>  
  
7.  <span data-ttu-id="b3559-111">Na página Criar parâmetros, verifique se o pacote Lição 6.dtsx está selecionado e se o Escopo está definido como Pacote na lista de Propriedades de configuração; em seguida, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="b3559-111">On the Create Parameters page make sure the Lesson 6.dtsx package is selected, and the Scope is set to Package, in the Configuration Properties List, then Click Next.</span></span>  
  
8.  <span data-ttu-id="b3559-112">Na página Configurar parâmetros, verifique se os valores de Nome e Valor são os mesmos nome e valor especificados na Lição 5 para a variável e o valor de configuração; então, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="b3559-112">On the Configure Parameters page verify that the values for Name and Value are the same name and value specified in Lesson 5 for the variable and configuration value, then click Next.</span></span>  
  
9. <span data-ttu-id="b3559-113">Na página Revisar, no painel Resumo, observe que o assistente usou as informações do arquivo de configuração para definir as Propriedades a serem convertidas.</span><span class="sxs-lookup"><span data-stu-id="b3559-113">On the Review page, in the Summary pane, notice that the wizard has used the information from the configuration file to set the Properties to be converted.</span></span>  
  
10. <span data-ttu-id="b3559-114">Clique em Converter.</span><span class="sxs-lookup"><span data-stu-id="b3559-114">Click Convert.</span></span>  
  
     <span data-ttu-id="b3559-115">Quando a conversão for concluída, uma mensagem é exibida avisando que as alterações não serão salvas até que o projeto seja salvo no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b3559-115">When the conversion completes a message is displayed warning that the changes are not saved until the project is saved in Visual Studio.</span></span> <span data-ttu-id="b3559-116">Clique em OK na caixa de diálogo de aviso.</span><span class="sxs-lookup"><span data-stu-id="b3559-116">Click OK on the warning dialog.</span></span>  
  
11. <span data-ttu-id="b3559-117">No Assistente de conversão de projeto do Integration Services, clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="b3559-117">On the Integration Services Project Conversion Wizard click Close.</span></span>  
  
12. <span data-ttu-id="b3559-118">No SQL Server Data Tools, clique no menu Arquivo e então em Salvar para salvar o pacote convertido.</span><span class="sxs-lookup"><span data-stu-id="b3559-118">In SQL Server Data Tools, click the File menu, then click Save to save the converted package.</span></span>  
  
13. <span data-ttu-id="b3559-119">Clique na guia parâmetros e verifique se o pacote agora contém um parâmetro para VarFolderName e o valor é o mesmo caminho especificado para a pasta Novos dados de exemplo, do arquivo de configuração da Lição 5.</span><span class="sxs-lookup"><span data-stu-id="b3559-119">Click the Parameters Tab and verify that the package now contains a parameter for VarFolderName and that the value is the same path specified for the New Sample Data folder from the Lesson 5 configuration file.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b3559-120">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="b3559-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b3559-121">Etapa 3: Testar o pacote da Lição 6</span><span class="sxs-lookup"><span data-stu-id="b3559-121">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
  
