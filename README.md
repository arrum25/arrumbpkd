# arrumbpkd

<!-- <pre><?php print_r($_SESSION); ?></pre> -->




<div class="row">
   	<div class="col-md-12">
                    <!-- Advanced Tables -->
        <div class="panel panel-default">
            <div class="panel-heading">
                            <h3>Badan Pengelola Keuangan Daerah</h3>
                </div>
                    <div class="panel-body">
                        <div class="table-responsive">
                            <table class="table table-striped table-bordered table-hover" id="dataTables-example">
                                <thead>
                                    <tr>
                                        <th>no</th>
										<th>Jenis Kendaraan</th>
										<th>Merk</th>
										<th>Tahun Pembuatan</th>
										<th>Nomor Rangka </th>
										<th>Nomor Mesin</th>
										<th>Aksi</th>
										
                                    </tr>
                                </thead>
                                <tbody>
                                    <?php $nomor=1; ?>
									<?php $ambil=$koneksi->query("SELECT * FROM pkb "); ?>
									<?php while($pecah = $ambil->fetch_assoc()){ ?>
										
									<tr>
										<th><?php echo $nomor; ?></th>
										<td><?php echo $pecah['JenisKendaraan']; ?></td>
										<td><?php echo $pecah['MerkKendaraan']; ?></td>
										<td><?php echo $pecah['TahunBuatan']; ?></td>
										<td><?php echo $pecah['NomorRangka']; ?></td>
										<td><?php echo $pecah['NomorMesin']; ?></td>
										
										<td>
											<div class="btn-group">
												<button data-toggle="dropdown" class="btn btn-default dropdown-toggle"><span class="caret"></span></button>
											  <ul class="dropdown-menu" >
												<li><a href="index.php?halaman=detailskripsi&id=<?php echo $pecah['Npm']; ?>" class="btn btn-info"><i class="fa fa-eye"></i>detail</a></li>
												<li><a href="index.php?halaman=detailskripsi&id=<?php echo $pecah['Npm']; ?>" class="btn btn-warning"><i class="fa fa-edit "></i>Ubah</a></li>
												<li><a onclick="return confirm('Apakah Anda yakin menghapus data ini?')" href="index.php?halaman=hapusjadwal&id=<?php echo $pecah['Npm']; ?>" class="btn btn-danger"><i class="fa fa-trash"></i>delete</a></li>
												
												
											  </ul>
											</div>
										</td>
									</tr>
									<?php $nomor++ ?>
									<?php } ?>
									
								</tbody>
							</table>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>
