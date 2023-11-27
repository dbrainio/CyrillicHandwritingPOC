# CyrillicHandwritingPOC
Repository for contributions for Data Generation for Post-OCR correction of Cyrillic handwriting paper
![Handwriting comparison](/images/handwriting_comparison.png)


## Abstract
>This paper introduces a novel approach to post-Optical Character Recognition Correction (POC) for handwritten Cyrillic text, addressing a significant gap in current research methodologies. This gap is due to the lack of large text corporas that provide OCR errors for further training of language-based POC models, which are demanding in terms of corpora size. Our study primarily focuses on the development and application of a synthetic handwriting generation engine based on Bézier curves. Such an engine generates highly realistic handwritten text in any amounts, which we utilize to create a substantial dataset by transforming Russian text corpora sourced from the internet. We apply a Handwritten Text Recognition (HTR) model to this dataset to identify OCR errors, forming the basis for our post-OCR correction model training. The correction model is trained on a 90-symbol input context, utilizing a pre-trained T5 architecture with a seq2seq correction task. We evaluate our approach on HWR200 and School_notebooks_RU datasets as they provide significant challenges in the HTR domain. Furthermore, POC can be used to highlight errors for teachers, evaluating student performance. This can be done simply by comparing sentences before and after correction, displaying differences in text. Our primary contribution lies in the innovative use of Bézier curves for Cyrillic text generation and subsequent error correction using a specialized POC model. We validate our approach by presenting Word Accuracy Rate (WAR) and Character Accuracy Rate (CAR) results, both with and without post-OCR correction, using real open corporas of handwritten Cyrillic text. These results, coupled with our methodology, are designed to be reproducible, paving the way for further advancements in the field of OCR and handwritten text analysis.

## Contributions

### Russian Essays Text Corpora
To match text distribution of handwritten Russian Essays we scraped Russian Internet sites that host essay examples for students and practice books. Resulting corpora consists of a total of 3.91M sentences or 284M symbols. Here is an example of one of the Essays:
>Как найти свое призвание в жизни? Именно над это проблемой размышляет автор данного текста. Антон Павлович Чехов показывает на ситуацию, где героиня находится в смятении при выборе своей дальнейшей карьеры и просит совета у своего товарища. Николай Степанович не спешит ей ответить, такой вопрос требует индивидуального подхода: « Но ответить что-нибудь нужно…» - на мой взгляд, этими словами писатель хотел показать, что по вопросам определения своего жизненного пути не стоит обращаться к кому-то, потому что никто не знает человека так хорошо, как он сам. Еще одним примером может послужить цитата: «… ты жертва не борьбы, а своего бессилия». Я думаю, что этой фразой Чехов хотел еще раз подчеркнуть, что правильно найти свой жизненный путь сможет лишь тот, кто прикладывает к этому усилия. Действительно, оба примера показывают, что отыскать дело своей жизни очень затруднительно, а еще сложнее помочь кому-то с этой непростой задачей. Позиция автора очевидна: А.П. Чехов считает, что найти свое призвание в жизни сможет лишь тот, кто самостоятельно подойдет к решению этого вопроса и сможет адекватно оценить все свои сильные и слабые стороны. Я согласна с авторской позицией, лишь сам человек может выбрать для себя истинный жизненный путь. Известно, что изначально А.П. Чехов был врачом, а лишь позже стал писателем. На его примере можно увидеть, что через годы поиска дела всей жизни, не прислушиваясь к мнению людей, которые считали, что у автора нет таланта, он смог найти истинный путь. Подводя итог, хотелось бы сказать, что найти свое призвание в жизни тяжело, но если приложить к этому массу усилий, принимать важные решения самостоятельно, понять, к чему лежит душа, то эти поиски обязательно дадут результат.
> 
[Download Link](https://drive.google.com/file/d/1mvnmxerks8kd6Bggj6opkuRZ5BW8cv1n/view?usp=sharing)

### Synthetic Handwritten Essays
For now code for generating handwritten text is still in development, but for evaluation purposes we provide a sample of generated handwritten essays that were used in the process of obtaining HTR errors. This dataset may be valuable for pre-training Cyrillic HTR models because of the scarcity of available HTR datasets. Here is an example of one generated essay:  

![Synthetic example](/images/4896.jpg)  

[Download Link](https://drive.google.com/file/d/1AVBArs2loq94zj6YM65kpjaznOodS_Ys/view?usp=sharing)

## Useful links
For ease of access we also provide links to related resources, used in this paper:

* [Google's mT5 Transformer model on HuggingFace](https://huggingface.co/google/mt5-base)  
* [Cointegrated mT5 Transformer model on HuggingFace](https://huggingface.co/cointegrated/rut5-base-multitask)  
* [Antiplagiat HWR200 Dataset on HuggingFace](https://huggingface.co/datasets/AntiplagiatCompany/HWR200)  
* [Sber's School Notebooks dataset on HuggingFace](https://huggingface.co/datasets/ai-forever/school_notebooks_RU)  
