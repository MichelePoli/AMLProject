5 graph tuning aggiungere solo dice

report
- tuning mike scrittura
- giorgia i dati

- related work
aggiungere qualcosa sulla domain adaptation -> paper loveda
- dati solo in experiment
- immagini loveda
- immagini pidnet rete

tabelle più grosse


(Figure \ref{fig:data_aug})


		\begin{figure}[H] 

			\centering
			\includegraphics[width=1\linewidth]{image/urban+mask1.png}

		\label{fig:urban_image}

		\caption{Satellite imagery (left) and its segmented land-use classification map (right) of an urban area}
		\end{figure}



\begin{figure}[H]  

			\centering
			\begin{minipage}{1\linewidth}
				\centering
				\includegraphics[width=1\linewidth]{image/urban+mask4.png}
				
				% \label{fig:dataset_rural_image1}
				
			\end{minipage}
			\begin{minipage}{1\linewidth}
				\centering
				\includegraphics[width=1\linewidth]{image/rural+mask4.png}
				
				% \label{fig:dataset_rural_image2}
				
			\end{minipage}
			\caption{Class distribution similarities between urban (top) and rural (bottom) domains in LoveDA: The background class dominates both domains.}  
			\label{fig:class_eug}  

		\end{figure}



\begin{figure}[H]
			\centering
			\begin{minipage}{0.48\linewidth}
				\centering
				\includegraphics[width=1\linewidth]{image/rural_1.png}
				
				% \label{fig:dataset_rural_image1}
				% \caption{rural image}
				
			\end{minipage}
			\begin{minipage}{0.48\linewidth}
				\centering
				\includegraphics[width=1\linewidth]{image/rural_2.png}
				
				
				% \caption{rural image}
				
			\end{minipage}
			\caption{rural image}
			\label{fig:dataset_rural_image1}

			\hfill
			\\
			\begin{minipage}{0.48\linewidth}
				\centering
				\includegraphics[width=1\linewidth]{image/urban_2.png}
				
				
				% \label{fig:dataset_urban_image1}
				% \caption{urban image }
				
			\end{minipage}
			\begin{minipage}{0.48\linewidth}
				\centering
				\includegraphics[width=1\linewidth]{image/urban_1.png}
				
				
				% \label{fig:dataset_urban_image2}
				
				
			\end{minipage}

			\caption{urban image }
			\label{fig:transfer}

		\end{figure}


\end{multicols}
Image
\begin{multicols}{2}


\begin{table}[H]
			\centering
			\renewcommand{\arraystretch}{1.4} % Aumenta lo spazio tra le righe per leggibilità
			\setlength{\tabcolsep}{6pt} % Regola la spaziatura tra colonne
			
			\resizebox{\linewidth}{!}{%
			\begin{tabular}{|l|c|}
				\hline
				Configuration & Best Validation mIoU (\%) \\ \hline
				Batch Size = 16, LR = \(10^{-4}\) (Default)  & 30.63 \\ \hline
				Batch Size = 2, LR = \(10^{-4}\)  & 15.00 \\ \hline
				Batch Size = 8, LR = \(10^{-4}\)  & 16.59 \\ \hline
				Batch Size = 16, LR = \(10^{-3}\)  & 19.09 \\ \hline
				Batch Size = 16, Adaptive Lambda  & 18.26 \\ \hline
			\end{tabular}
			}
			\caption{Performance comparison of different models on urban images.}
			\label{tab:hyperparameters}

		\end{table}