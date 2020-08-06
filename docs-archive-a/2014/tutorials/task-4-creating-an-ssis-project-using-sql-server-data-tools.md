---
title: 'Tarefa 4: Criando um projeto do SSIS usando SQL Server Data Tools | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 8603ea91-2ec4-40b6-8070-4f824332f5d3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 07976dbd2c84b1385d79ce3f4ce4f616e0f706b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681287"
---
# <a name="task-4-creating-an-ssis-project-using-sql-server-data-tools"></a>Tarefa 4: Criando um projeto SSIS usando o SQL Server Data Tools
  Nesta tarefa, você cria um projeto do SSIS usando **SQL Server Data Tools** para automatizar a limpeza e a correspondência de dados do fornecedor.

1.  Inicie o **SQL Server Data Tools**. Clique em Iniciar, aponte para **todos os programas**, expanda **Microsoft SQL Server 2012**e clique em **SQL Server Data Tools**.

2.  No menu **Arquivo** , aponte para **Novo**e clique em **Projeto**.

3.  Expanda **Business Intelligence** no painel **modelos instalados** e selecione **Integration Services**.

     ![Visual Studio - Caixa de diálogo Novo Projeto](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - Caixa de diálogo Novo Projeto")

4.  Selecione **Integration Services projeto** na **lista de tipos de projeto**.

5.  Digite **CleanseAndCurateSuppliers** para **nome** e clique em **OK**.

6.  Na janela **Gerenciador de soluções** , clique com o botão direito do mouse em **Package. dtsx** e selecione **renomear**. Se você não vir **Gerenciador de soluções** janela, clique em **Exibir** na barra de menus e clique em **Gerenciador de soluções**.

     ![Package.dtsx - Menu Renomear](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Menu Renomear")

7.  Digite **CleanseAndCurate. dtsx** e pressione **Enter**. Certifique-se de que a **extensão** permaneça **. dtsx**.

## <a name="next-step"></a>Próxima etapa
 [Tarefa 5: Adicionando a tarefa de fluxo de dados](task-5-adding-data-flow-task.md)


