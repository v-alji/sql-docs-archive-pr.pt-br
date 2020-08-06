---
title: Editar as propriedades do banco de dados Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraProp
ms.assetid: 58dc99f1-ee6b-4508-bb66-2bc589611ff7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3cad2735e6cd6095f9730f3b4e7228526451d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572141"
---
# <a name="edit-the-oracle-database-properties"></a><span data-ttu-id="bbb73-102">Editar as propriedades do banco de dados Oracle</span><span class="sxs-lookup"><span data-stu-id="bbb73-102">Edit the Oracle Database Properties</span></span>
  <span data-ttu-id="bbb73-103">Use a guia Oracle no editor de Propriedades para fazer alterações na descrição fornecida na página Create CDC database no assistente de Nova Instância e fazer alterações nas informações de conexão de banco de dados de mineração de logs do Oracle.</span><span class="sxs-lookup"><span data-stu-id="bbb73-103">Use the Oracle tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
 <span data-ttu-id="bbb73-104">Veja a seguir a descrição das informações na guia **Oracle** .</span><span class="sxs-lookup"><span data-stu-id="bbb73-104">The following describes the information in the **Oracle** tab.</span></span>  
  
 <span data-ttu-id="bbb73-105">**Nome**</span><span class="sxs-lookup"><span data-stu-id="bbb73-105">**Name**</span></span>  
 <span data-ttu-id="bbb73-106">O nome da Instância CDC inserido na página Create CDC Database no New Instance Wizard.</span><span class="sxs-lookup"><span data-stu-id="bbb73-106">The name of the CDC Instance that you entered in the Create CDC Database page in the New Instance wizard.</span></span> <span data-ttu-id="bbb73-107">Este campo é somente leitura e você não pode editar essas informações.</span><span class="sxs-lookup"><span data-stu-id="bbb73-107">This field is read only and you cannot edit this information.</span></span>  
  
 <span data-ttu-id="bbb73-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bbb73-108">**Description**</span></span>  
 <span data-ttu-id="bbb73-109">Você pode editar a descrição da nova instância ou adicionar uma se não tiver feito, ao criar a Instância CDC.</span><span class="sxs-lookup"><span data-stu-id="bbb73-109">You can edit the description of the new instance or add one if you did not do so when creating the CDC Instance.</span></span>  
  
 <span data-ttu-id="bbb73-110">**Cadeia de conexão do Oracle**</span><span class="sxs-lookup"><span data-stu-id="bbb73-110">**Oracle Connect String**</span></span>  
 <span data-ttu-id="bbb73-111">A cadeia de conexão do Oracle no computador com o banco de dados Oracle que você está usando.</span><span class="sxs-lookup"><span data-stu-id="bbb73-111">The Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="bbb73-112">Este campo é somente leitura e você não pode editar essas informações.</span><span class="sxs-lookup"><span data-stu-id="bbb73-112">This field is read only and you cannot edit this information.</span></span> <span data-ttu-id="bbb73-113">Isto ocorre porque algumas alterações na cadeia de conexão podem apontar a Instância Oracle CDC para outro banco de dados Oracle inteiramente, corrompendo o estado da Instância CDC armazenada na tabela **cdc.xdbcdc_config** .</span><span class="sxs-lookup"><span data-stu-id="bbb73-113">This is because some changes to the connect string may point the Oracle CDC Instance to another Oracle database entirely, corrupting the CDC Instance state as stored in the **cdc.xdbcdc_config** table.</span></span> <span data-ttu-id="bbb73-114">Se for necessário realizar alterações secundárias, você poderá alterar a cadeia de conexão diretamente na tabela de configuração usando o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="bbb73-114">If minor changes are needed, you can change the connect string directly in the configuration table using SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="bbb73-115">**Autenticação de mineração de logs da Oracle**</span><span class="sxs-lookup"><span data-stu-id="bbb73-115">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="bbb73-116">Para inserir as credenciais de autenticação para o banco de dados Oracle que contém o minerador de logs, siga um destes procedimentos em **Autenticação**:</span><span class="sxs-lookup"><span data-stu-id="bbb73-116">To enter the authentication credentials for the Oracle database that contains the log miner, select one of the following under **Authentication**:</span></span>  
  
-   <span data-ttu-id="bbb73-117">**Autenticação do Windows**: selecione isto para usar as credenciais de domínio atuais do Windows.</span><span class="sxs-lookup"><span data-stu-id="bbb73-117">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="bbb73-118">Você só poderá usar esta opção se o banco de dados Oracle estiver configurado para funcionar com autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="bbb73-118">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="bbb73-119">**Autenticação do Oracle**: se você selecionou esta opção, deve digitar o **Nome de usuário** e **Senha** para o usuário no banco de dados Oracle ao qual você está se conectando.</span><span class="sxs-lookup"><span data-stu-id="bbb73-119">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
 <span data-ttu-id="bbb73-120">Você pode ver as propriedades do banco de dados Oracle no visualizador.</span><span class="sxs-lookup"><span data-stu-id="bbb73-120">You can view the Oracle database properties in the viewer.</span></span> <span data-ttu-id="bbb73-121">Ao usar o visualizador, as informações serão somente leitura.</span><span class="sxs-lookup"><span data-stu-id="bbb73-121">When using the viewer the information is read only.</span></span> <span data-ttu-id="bbb73-122">O visualizador também inclui uma lista das colunas capturadas na tabela.</span><span class="sxs-lookup"><span data-stu-id="bbb73-122">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="bbb73-123">Para obter mais informações sobre como acessar o visualizador, consulte [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="bbb73-123">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb73-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bbb73-124">See Also</span></span>  
 <span data-ttu-id="bbb73-125">[Como gerenciar um serviço CDC no CDC Designer Console](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="bbb73-125">[How to Manage a CDC Service from the CDC Designer Console](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span></span>  
 <span data-ttu-id="bbb73-126">[Conectar-se a um banco de dados de origem Oracle](connect-to-an-oracle-source-database.md) </span><span class="sxs-lookup"><span data-stu-id="bbb73-126">[Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md) </span></span>  
 [<span data-ttu-id="bbb73-127">Conectar-se ao Oracle</span><span class="sxs-lookup"><span data-stu-id="bbb73-127">Connect to Oracle</span></span>](connect-to-oracle.md)  
  
  
